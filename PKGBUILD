# Script generated with Bloom
pkgdesc="ROS - This package is basically an OpenSceneGraph (OSG) adaptation of the Interactive Markers client writen for rviz/Ogre."


pkgname='ros-kinetic-osg-interactive-markers'
pkgver='1.0.2_1'
pkgrel=1
arch=('any')
license=('BSD'
)

makedepends=('openscenegraph'
'ros-kinetic-catkin'
'ros-kinetic-interactive-markers'
'ros-kinetic-osg-markers'
'ros-kinetic-osg-utils'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

depends=('openscenegraph'
'ros-kinetic-interactive-markers'
'ros-kinetic-osg-markers'
'ros-kinetic-osg-utils'
'ros-kinetic-roscpp'
'ros-kinetic-tf'
'ros-kinetic-visualization-msgs'
)

conflicts=()
replaces=()

_dir=osg_interactive_markers
source=()
md5sums=()

prepare() {
    cp -R $startdir/osg_interactive_markers $srcdir/osg_interactive_markers
}

build() {
  # Use ROS environment variables
  source /usr/share/ros-build-tools/clear-ros-env.sh
  [ -f /opt/ros/kinetic/setup.bash ] && source /opt/ros/kinetic/setup.bash

  # Create build directory
  [ -d ${srcdir}/build ] || mkdir ${srcdir}/build
  cd ${srcdir}/build

  # Fix Python2/Python3 conflicts
  /usr/share/ros-build-tools/fix-python-scripts.sh -v 2 ${srcdir}/${_dir}

  # Build project
  cmake ${srcdir}/${_dir} \
        -DCMAKE_BUILD_TYPE=Release \
        -DCATKIN_BUILD_BINARY_PACKAGE=ON \
        -DCMAKE_INSTALL_PREFIX=/opt/ros/kinetic \
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

