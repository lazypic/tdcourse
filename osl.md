# Open Shanding Language
최초 소니이미지 픽쳐스에서 아놀드 렌더러에 사용하기 위해서 만들어진 쉐이딩 렝귀지 입니다.

쉐이더를 만들기 위한 언어입니다. 많은 렌더러들이 지원하며 렌더러마다 약간의 문법은 다릅니다.
쉐이더를 작성할 때 조금 수고 스럽더라도 OSL로 작성하면 라이브러리화 하기 쉽습니다.
다른 렌더러로 전환되더라도 재활용하기가 편리합니다.

지원하는 렌더러는 아래와 같습니다.

- Pixar: [PhotoRealistic RenderMan RIS](https://renderman.pixar.com)
- [Autodesk/SolidAngle: Arnold](https://www.autodesk.com/products/arnold/overview)
- [DNA Research: 3Delight (Katana Default Renderer)](https://www.3delight.com)
- [Chaos Group: V-Ray](https://docs.chaosgroup.com/display/VRAY3MAX/OSL+Material+%7C+VRayOSLMtl)
- [Autodesk: 3DS Max 2019](https://knowledge.autodesk.com/support/3ds-max/getting-started/caas/CloudHelp/cloudhelp/2019/ENU/3DSMax-Lighting-Shading/files/GUID-568DA829-62DA-432F-814F-2600F65141BD-htm.html)
- [Blender/Cycles](https://code.blender.org/2012/09/open-shading-language-in-cycles/)
- Sony Pictures Imageworks: in-house "Arnold" renderer
- [Isotropix: Clarisse](https://www.isotropix.com)
- [Autodesk Beast](https://www.youtube.com/watch?v=z1SSxOIOx7Y)
- Opensource Renderer [Appleseed](https://github.com/appleseedhq/appleseed)
- [Animal Logic: Glimpse renderer](https://www.fxguide.com/featured/a-glimpse-at-animal-logic/)
- [Image Engine: Gaffer (for expressions and deformers)](http://www.gafferhq.org)
- Ubisoft motion picture group's proprietary renderer

## 언어구성
보통 아래 형태의 언어를 띕니다. C++ 코드와 비슷하게 생겼습니다.

아래는 OSL 파일의 한 예입니다.
```
#include <stdosl.h>

shader TDdiffuse_ramp(
        normal Normal = N,
        color Color1 = color(0.8, 0.0, 0.0),
        color Color2 = color(0.0, 0.8, 0.0),
        color Color3 = color(0.0, 0.0, 0.8),
        color Color4 = 0.1,
        color Color5 = 0.2,
        color Color6 = 0.3,
        color Color7 = 0.4,
        color Color8 = 0.5,
        output closure color BSDF = 0 )
{
    color Color[8] = {Color1, Color2, Color3, Color4, Color5, Color6, Color7, Color8};

    BSDF = diffuse_ramp(Normal, Color);
}
```

## Unreal
아직 지원하고 있지 않습니다. 아래 URL에서 해당 사항에 대해서 Discussion은 올라와 있습니다.
https://forums.unrealengine.com/development-discussion/rendering/36083-osl-support

## Reference
- https://github.com/imageworks/OpenShadingLanguage
- https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=1&ved=2ahUKEwi5kfuTuYHfAhWBF4gKHaDGAVgQFjAAegQIChAC&url=https%3A%2F%2Fraw.githubusercontent.com%2Fimageworks%2FOpenShadingLanguage%2Fmaster%2Fsrc%2Fdoc%2Fosl-languagespec.pdf&usg=AOvVaw0fnZDAj-almK7unV7NKApA
- https://blendersushi.blogspot.com/2013/10/osl-basic-functions.html