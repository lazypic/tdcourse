# OpenColorIO LUT
OpenColorIO에서는 컬러컬렉션을 위해서 .cc, .ccc 파일을 사용합니다.
참고로 Sony Pictures Image 에서는 1D lut는 .spi1d, 3D lut는 .spi3d 포멧이 사용됩니다. 사실상 같은 포멧입니다.
OpenColorIO의 LUT는 xml 포멧으로 작성되어 있습니다.

## .cc
OCIO의 1D lut파일입니다.
일반적으로 VFX회사에서는 각각 하나하나의 샷을 그레이딩 하는 방법에 많이 사용하는 포멧입니다.
회사는 이 방식을 각 샷 컬러를 돌릴 때 파이프라인과 연계하는데 이 방식을 Natural grand pipeline 이라고 합니다.
회사마다 .cc 파일로 정보를 공유하기도, DB에 저장하기도, .exr 파일의 Attr 값을 이용하기도 합니다.

파일내부 구성은 아래와 같습니다.
```
<ColorCorrection id="mygrade">
        <SOPNode>
             <Slope>2 1 1</Slope>
             <Offset>0 0 0</Offset>
             <Power>1 1 1</Power>
        </SOPNode>
        <SATNode>
             <Saturation>1</Saturation>
        </SATNode>
</ColorCorrection>
```

- 참고 : http://opencolorio.org/userguide/contexts.html Per-shot grades 참고.

## .ccc
.cc파일의 그룹이라고 생각하면 됩니다. id를 이용해서 각 정보를 구분합니다.

```
<ColorCorrectionCollection xmlns="urn:ASC:CDL:v1.2">
<ColorCorrection id="FOO_0010">
        <SOPNode>
             <Slope>2 1 1</Slope>
             <Offset>0 0 0</Offset>
             <Power>1 1 1</Power>
        </SOPNode>
        <SATNode>
             <Saturation>1</Saturation>
        </SATNode>
</ColorCorrection>

<ColorCorrection id="BAR_0010">
        <SOPNode>
             <Slope>2 1 1</Slope>
             <Offset>0 0.1 0</Offset>
             <Power>1 1 1</Power>
        </SOPNode>
        <SATNode>
             <Saturation>1</Saturation>
        </SATNode>
</ColorCorrection>
</ColorCorrectionCollection>
```

뉴크에서 OCIOCDLTransform을 이용해서 파일을 로딩할 수 있습니다.
![nuke_ocio_cdl_transform](../figures/nuke_ocio_cdl_transform.png)

나트론 OCIOCDLTransform에서도 파일을 로딩할 수 있습니다.
![natron_ocio_cdl_transform](../figures/natron_ocio_cdl_transform.png)

## 실습
뉴크를 이용해서 .cc 파일을 만들어봅시다.

## Reference
http://opencolorio.org/userguide/contexts.html