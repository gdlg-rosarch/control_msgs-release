# Script generated with Bloom
pkgdesc="ROS - control_msgs contains base messages and actions useful for controlling robots. It provides representations for controller setpoints and joint and cartesian trajectories."
url='http://ros.org/wiki/control_msgs'

pkgname='ros-melodic-control-msgs'
pkgver='1.4.0_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('ros-melodic-actionlib-msgs'
'ros-melodic-catkin'
'ros-melodic-geometry-msgs'
'ros-melodic-message-generation'
'ros-melodic-std-msgs'
'ros-melodic-trajectory-msgs'
)

depends=('ros-melodic-actionlib-msgs'
'ros-melodic-geometry-msgs'
'ros-melodic-message-runtime'
'ros-melodic-std-msgs'
'ros-melodic-trajectory-msgs'
)

conflicts=()
replaces=()

_dir=control_msgs
source=()
md5sums=()

prepare() {
    cp -R $startdir/control_msgs $srcdir/control_msgs
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/melodic/setup.bash ] && source /opt/ros/melodic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/melodic \
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

