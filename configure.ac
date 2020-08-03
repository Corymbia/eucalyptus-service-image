AC_INIT([eucalyptus-service-image], [5.0.100])

INSTALL_TREE=http://linux.mirrors.es.net/centos/7/os/x86_64/
BASE_MIRROR=${INSTALL_TREE}
UPDATES_MIRROR=http://linux.mirrors.es.net/centos/7/updates/x86_64/
EPEL_MIRROR=http://linux.mirrors.es.net/epel/7/x86_64/
EUCALYPTUS_MIRROR=http://downloads.eucalyptus.com/software/eucalyptus/4.4/rhel/7/x86_64/
EUCA2OOLS_MIRROR=http://downloads.eucalyptus.com/software/euca2ools/3.3/rhel/7/x86_64/
BASEIMAGE=
USEBASEIMAGE=

AC_ARG_WITH(install-tree,
    [  --with-install-tree=<dir>       the location of the install tree],
    [INSTALL_TREE="${withval}"])
AC_ARG_WITH(base-mirror,
    [  --with-base-mirror=<dir>        the location of the base OS mirror],
    [BASE_MIRROR="${withval}"])
AC_ARG_WITH(updates-mirror,
    [  --with-updates-mirror=<dir>     the location of the updates mirror],
    [UPDATES_MIRROR="${withval}"])
AC_ARG_WITH(epel-mirror,
    [  --with-epel-mirror=<dir>        the location of the EPEL mirror],
    [EPEL_MIRROR="${withval}"])
AC_ARG_WITH(eucalyptus-mirror,
    [  --with-eucalyptus-mirror=<dir>  the location of the Eucalyptus mirror],
    [EUCALYPTUS_MIRROR="${withval}"])
AC_ARG_WITH(euca2ools-mirror,
    [  --with-euca2ools-mirror=<dir>   the location of the euca2ools mirror],
    [EUCA2OOLS_MIRROR="${withval}"])
AC_ARG_WITH(base-image-file,
    [  --with-base-image-file          the location of an existing base image],
    [USEBASEIMAGE="${withval}"])
AC_ARG_ENABLE(base-image-only,
    [  --enable-base-image-only        build a base image],
    [BASEIMAGE="true"])

AC_PATH_PROG(PYTHON, python)
AC_PATH_PROG(VIRSH, virsh)
AC_PATH_PROG(VIRT_INSTALL, virt-install)
AC_PATH_PROG(VIRT_SYSPREP, virt-sysprep)
AC_PATH_PROG(VIRT_SPARSIFY, virt-sparsify)

AC_CHECK_PROG(VIRT_SYSPREP_CHECK,virt-sysprep,yes)
if test x"$VIRT_SYSPREP_CHECK" != x"yes" ; then
    AC_MSG_ERROR([Please install virt-sysprep before continuing.])
fi
AC_CHECK_PROG(VIRT_SPARSIFY_CHECK,virt-sparsify,yes)
if test x"$VIRT_SPARSIFY_CHECK" != x"yes" ; then
    AC_MSG_ERROR([Please install virt-sparsify before continuing.])
fi
AC_CHECK_PROG(VIRT_INSTALL_CHECK,virt-install,yes)
if test x"$VIRT_INSTALL_CHECK" != x"yes" ; then
    AC_MSG_ERROR([Please install virt-install before continuing.])
fi

AC_CONFIG_FILES([
    Makefile
    eucalyptus-service-image.ks
    eucalyptus-service-image-post.sh
])
AC_SUBST(INSTALL_TREE)
AC_SUBST(BASE_MIRROR)
AC_SUBST(UPDATES_MIRROR)
AC_SUBST(EPEL_MIRROR)
AC_SUBST(EUCALYPTUS_MIRROR)
AC_SUBST(EUCA2OOLS_MIRROR)
AC_SUBST(VIRSH)
AC_SUBST(VIRT_INSTALL)
AC_SUBST(VIRT_SYSPREP)
AC_SUBST(VIRT_SPARSIFY)
AC_SUBST(BASEIMAGE)
AC_SUBST(USEBASEIMAGE)
AC_OUTPUT
