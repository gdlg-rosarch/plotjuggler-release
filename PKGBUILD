# Script generated with Bloom
pkgdesc="ROS - PlotJuggler: juggle with data"
url='https://github.com/facontidavide/PlotJuggler'

pkgname='ros-lunar-plotjuggler'
pkgver='1.5.1_1'
pkgrel=1
arch=('any')
license=('LGPLv3'
)

makedepends=('binutils'
'qt5-base'
'qt5-svg'
'ros-lunar-catkin'
'ros-lunar-ros-type-introspection'
'ros-lunar-rosbag'
'ros-lunar-rosbag-storage'
'ros-lunar-roscpp'
'ros-lunar-roscpp-serialization'
'ros-lunar-rostime'
'ros-lunar-topic-tools'
)

depends=('binutils'
'qt5-base'
'qt5-svg'
'ros-lunar-ros-type-introspection'
'ros-lunar-rosbag'
'ros-lunar-rosbag-storage'
'ros-lunar-roscpp'
'ros-lunar-roscpp-serialization'
'ros-lunar-rostime'
'ros-lunar-topic-tools'
)

conflicts=()
replaces=()

_dir=plotjuggler
source=()
md5sums=()

prepare() {
    cp -R $startdir/plotjuggler $srcdir/plotjuggler
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/lunar/setup.bash ] && source /opt/ros/lunar/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/lunar \
        -DPYTHON_EXECUTABLE=/usr/bin/python2 \
        -DPYTHON_INCLUDE_DIR=/usr/include/python2.7 \
        -DPYTHON_LIBRARY=/usr/lib/libpython2.7.so \
        -DPYTHON_BASENAME=-python2.7 \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}

