```
yum update
yum groupinstall "Development Tools" "Additional Development"
yum install fribidi-devel git jansson-devel libogg-devel libsamplerate-devel libtheora-devel libvorbis-devel opus-devel
yum install libass-devel yasm
yum repo-pkgs zmrepo remove
yum remove zmrepo
sudo yum localinstall --nogpgcheck https://download1.rpmfusion.org/free/el/rpmfusion-free-release-7.noarch.rpm
sudo yum install lame-devel x264-devel
```

https://handbrake.fr/docs/en/1.1.0/developer/build-linux.html

###
```
git clone https://github.com/HandBrake/HandBrake.git && cd HandBrake
git tag --list | grep ^1\.1\.
git checkout refs/tags/$(git tag -l | grep -E '^1\.1\.[0-9]+$' | tail -n 1)
./configure --launch-jobs=$(nproc) --launch
sudo make --directory=build install
rm -rf build
```
