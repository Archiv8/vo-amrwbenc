#!/bin/bash

# Disable various shellcheck rules that produce false positives in this file.
# Repository rules should be added to the .shellcheckrc file located in the
# repository root directory, see https://github.com/koalaman/shellcheck/wiki
# and https://archiv8.github.io for further information.
# shellcheck disable=SC2034,SC2154
# [ToDo]: Add files: User documentation
# [ToDo]: Add files: Tooling
# [FixMe]: Namcap warnings and errors

# Maintainer: Ross Clark <archiv8@artisteducator.com>
# Contributor: Ross Clark <archiv8@artisteducator.com>

pkgname=vo-amrwbenc
pkgver=0.1.3
pkgrel=3
pkgdesc="Library for the VisualOn Adaptive Multi Rate Wideband (AMR-WB) audio encoder"
arch=("x86_64")
url="http://sourceforge.net/projects/opencore-amr/"
license=("APACHE")
depends=(
    # Arch Linux dependencies
    "glibc"
)
source=(
    "http://downloads.sourceforge.net/project/opencore-amr/vo-amrwbenc/${pkgname}-${pkgver}.tar.gz"
    )
sha512sums=(
    "5f132f798f00ec2c0619700ab1ce456897792b45631af4b538c866636af9c9de5600af5f79040c41c3dc69c17cf4be7032139a9518a46a4276431e091f3dd6a9"
    )

build() {
    cd "${pkgname}-${pkgver}"
    ./configure --prefix="/usr"
    make
}

package() {
    cd "${pkgname}-${pkgver}"
    make DESTDIR="$pkgdir" install
    install -D -m644 NOTICE -t "${pkgdir}/usr/share/licenses/${pkgname}"
}
