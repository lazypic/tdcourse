# Boost

#### Boost 컴파일
VFX Reference Platform 2021 기준 Boost는 1.73을 사용합니다.
abcview, oiiotool 등의 명령어를 컴파일 하기 위해서는 Boost가 필요합니다.

이 작업은 오래걸립니다. 수업 초반에 진행하는 것이 좋습니다.

```bash
cd ~/app
wget https://sourceforge.net/projects/boost/files/boost/1.73.0/boost_1_73_0.tar.gz
tar -zxvf boost_1_73_0.tar.gz
rm boost_1_73_0.tar.gz
mv boost_1_73_0 boost_1_73_0_src
mkdir boost_1_73_0
cd boost_1_73_0_src
./bootstrap.sh --prefix=$HOME/app/boost_1_73_0
./b2 install
```