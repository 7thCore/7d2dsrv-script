#    Copyright (C) 2022 7thCore
#    This file is part of 7d2dSrv-Script.
#
#    7d2dSrv-Script is free software: you can redistribute it and/or modify
#    it under the terms of the GNU General Public License as published by
#    the Free Software Foundation, either version 3 of the License, or
#    (at your option) any later version.
#
#    7d2dSrv-Script is distributed in the hope that it will be useful,
#    but WITHOUT ANY WARRANTY; without even the implied warranty of
#    MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#    GNU General Public License for more details.
#
#    You should have received a copy of the GNU General Public License
#    along with this program.  If not, see <http://www.gnu.org/licenses/>.

pkgname=7d2dsrv-script
pkgver=1.0
pkgrel=8
pkgdesc='7 Days to Die server script for running the server on linux.'
arch=('x86_64')
license=('GPL3')
depends=('bash'
         'coreutils'
         'sudo'
         'grep'
         'sed'
         'awk'
         'curl'
         'rsync'
         'wget'
         'findutils'
         'tmux'
         'jq'
         'zip'
         'unzip'
         'p7zip'
         'postfix'
         's-nail'
         'steamcmd')
install=7d2dsrv-script.install
source=('bash_profile'
        '7d2dsrv-mkdir-tmpfs@.service'
        '7d2dsrv-script.bash'
        '7d2dsrv-send-notification@.service'
        '7d2dsrv@.service'
        '7d2dsrv-timer-1.service'
        '7d2dsrv-timer-1.timer'
        '7d2dsrv-timer-2.service'
        '7d2dsrv-timer-2.timer'
        '7d2dsrv-tmpfs@.service')
sha256sums=('f1e2f643b81b27d16fe79e0563e39c597ce42621ae7c2433fd5b70f1eeab5d63'
            '0491f13de4db45c73e61955dddb3f08a30adec6692622c9e3858d465573731a3'
            '85bf3edfb6b8dac90ab0fd6740018e05903ebed76801c4c35ecf76ca80945593'
            '231dd14403fa38f40a0df6f395b5e70e0dbad6fa0cadbfb54b0005c33df20771'
            '11ab259f31f7dcab6af2e7714450e7ca218d072e866c3ae4677f159cd452b234'
            '302e410768b8940d5fdcd2ec2f731a95329d00bcdff164f4814e28efc1fd11b2'
            'd5f7734ef8fe4d32e47b17742e5b2f062d3015c80991eac77db751b33c528870'
            '4fb1ccdfb9d9be4d9b5adae7cd747ee5d21e5520342fdfa1902163968a1ed170'
            'a1ed17bfc32e5c32c90d8c0df1a29fb059fc97862735842435636ec934f4b955'
            '6223f9fb3efcf374e543aaf960faf241e437fb0eb323314c2e8cf8572024b540')

package() {
  install -d -m0755 "${pkgdir}/usr/bin"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/server"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/config"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/updates"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/backups"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/logs"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/tmpfs"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/.config"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/.config/systemd"
  install -d -m0755 "${pkgdir}/srv/7d2dsrv/.config/systemd/user"
  install -D -Dm755 "${srcdir}/7d2dsrv-script.bash" "${pkgdir}/usr/bin/7d2dsrv-script"
  install -D -Dm755 "${srcdir}/7d2dsrv-timer-1.timer" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv-timer-1.timer"
  install -D -Dm755 "${srcdir}/7d2dsrv-timer-1.service" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv-timer-1.service"
  install -D -Dm755 "${srcdir}/7d2dsrv-timer-2.timer" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv-timer-2.timer"
  install -D -Dm755 "${srcdir}/7d2dsrv-timer-2.service" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv-timer-2.service"
  install -D -Dm755 "${srcdir}/7d2dsrv-send-notification@.service" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv-send-notification@.service"
  install -D -Dm755 "${srcdir}/7d2dsrv@.service" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv@.service"
  install -D -Dm755 "${srcdir}/7d2dsrv-mkdir-tmpfs@.service" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv-mkdir-tmpfs@.service"
  install -D -Dm755 "${srcdir}/7d2dsrv-tmpfs@.service" "${pkgdir}/srv/7d2dsrv/.config/systemd/user/7d2dsrv-tmpfs@.service"
  install -D -Dm755 "${srcdir}/bash_profile" "${pkgdir}/srv/7d2dsrv/.bash_profile"
}
