ssh -T -v git@github.com的登录出现


    OpenSSH_7.3p1, OpenSSL 1.0.2j  26 Sep 2016
    debug1: Reading configuration data /etc/ssh/ssh_config
    debug1: Connecting to github.com [1.111.11.111] port 22.
    debug1: Connection established.
    debug1: identity file /home/arch/.ssh/id_rsa type 1
    debug1: key_load_public: No such file or directory
    debug1: identity file /home/arch/.ssh/id_rsa-cert type -1
    debug1: key_load_public: No such file or directory
    debug1: identity file /home/arch/.ssh/id_dsa type -1
    debug1: key_load_public: No such file or directory
    debug1: identity file /home/arch/.ssh/id_dsa-cert type -1
    debug1: key_load_public: No such file or directory
    debug1: identity file /home/arch/.ssh/id_ecdsa type -1
    debug1: key_load_public: No such file or directory
    debug1: identity file /home/arch/.ssh/id_ecdsa-cert type -1
    debug1: key_load_public: No such file or directory
    debug1: identity file /home/arch/.ssh/id_ed25519 type -1
    debug1: key_load_public: No such file or directory
    debug1: identity file /home/arch/.ssh/id_ed25519-cert type -1
    debug1: Enabling compatibility mode for protocol 2.0
    debug1: Local version string SSH-2.0-OpenSSH_7.3
    ssh_exchange_identification: Connection closed by remote host




经网上查阅，知道ip地址是1.1.11.111是韩国的地址，网上说是中间人攻击，DNS的解析不正确，因此把/etc/resovf.conf的域名服务器地址改成8.8.8.8后，问题解决。

经验：一开始以为是arch linux的22端口没有开放，往那个方向排错了很长一段时间。后来还是把ssh -v整个放网上一搜出了一个结果。看来以后排错要从一开始才行。
