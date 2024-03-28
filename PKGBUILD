# Script generated with import_catkin_packages.py
# For more information: https://github.com/bchretien/arch-ros-stacks
pkgdesc="ROS - Package containing PCL (Point Cloud Library)-related ROS messages."
url='https://wiki.ros.org/pcl_msgs'

pkgname='ros-noetic-pcl-msgs'
pkgver='0.3.0'
_pkgver_patch=0
arch=('any')
pkgrel=2
license=('BSD')

ros_makedepends=(ros-noetic-catkin
  ros-noetic-message-generation
  ros-noetic-sensor-msgs
  ros-noetic-std-msgs)
makedepends=('cmake' 'ros-build-tools'
  ${ros_makedepends[@]})

ros_depends=(ros-noetic-message-runtime
  ros-noetic-sensor-msgs
  ros-noetic-std-msgs)
depends=(${ros_depends[@]})

# Git version (e.g. for debugging)
# _tag=release/noetic/pcl_msgs/${pkgver}-${_pkgver_patch}
# _dir=${pkgname}
# source=("${_dir}"::"git+https://github.com/ros-gbp/pcl_msgs-release.git"#tag=${_tag})
# sha256sums=('SKIP')

# Tarball version (faster download)
_commit="89b072539778246218e94b608f9f294987bb6d0a"
_dir="pcl_msgs-${_commit}/"
source=("${pkgname}-${pkgver}.tar.gz"::"https://github.com/ros-perception/pcl_msgs/archive/${_commit}.tar.gz")
sha256sums=('eaf3f1c1bffaf248bf339b47c6d9584aeac60f62d65454f4f86a76094ae7f1ed')

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/noetic/setup.bash ] && source /opt/ros/noetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/noetic \
        -DPYTHON_EXECUTABLE=/usr/bin/python \
        -DSETUPTOOLS_DEB_LAYOUT=OFF
  make
}

package() {
  cd "${srcdir}/build"
  make DESTDIR="${pkgdir}/" install
}
