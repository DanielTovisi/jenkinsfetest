pipeline {
     agent any
     tools {nodejs "17.9.0"}
     stages {
        stage("Build") {
            steps {
                sh 'npm install'
                sh "npm run build"
            }
        }
        def remote = [:]
        remote.name = 'test'
        remote.host = '35.156.239.114'
        remote.user = 'root'
        remote.passphrase = "-----BEGIN RSA PRIVATE KEY-----
MIIEpAIBAAKCAQEAo3PTPuStWDL9CanO+LJEUQwIHlkw/t7t6VQqCXdSorGgg9/O
OfyGJwtXkIrfUXvDXRAgEfrChg2wxEltZHEdCH03zjneoQ4hDkDP4FPe0FJsB4Y6
HXfUQRpKZ3S/gebrtmtk3cRetwIr0mtON4xiCMbxmG+MgjEC/r1y316JwRzxln3r
8dkV1U7X72hs05F6MKH39rpBO/2cllspucbE1r6BqIIy1QBPap5Y7tYhcemKm5dK
bJKUCVZRPO8aehp0RCSzU4oOnZXL3G/+SXIwwQW8OC7f47F7m2VHFxHUQvUTcyKG
BR9som7FtPQkT5uNbB3EKTyFT3XSa2ML2H4tUwIDAQABAoIBAQCXxJA9MbAS2SVC
t71KBpyQdI+FPmPUA8L8h/2QVI8SKcRVLpYaGXOnBU0FFS1OR5Ca9MISb7f3KPcd
CuDcBntiyoHqpqkk+i2PQnbCYJ3e6OkOA4AqpH0dBgBYF3tKbtQmyYkasZ8QZp+x
/Zje0yaj57WkSM86g6+4QMhMx0c5Wt4bZ3dGktEeLSFyHaAP9sUs3nzCAC89kzLD
hNLjTVm7N08tJr9OYKmvmpPdbbW6WLLSUmEeyQpusutWX1/z75/ssrUDzTBYDcRb
i5HEJaxQiroKvEY1KmyNn08Eh3EQWW0vCWigpA4ngNh/inkDvI/JfIbavSKxaZHj
rDhhP+rhAoGBANkWuFFq4QElDyGdo0YBzAM3joLptTW+pc96ml+ChHhosbsuV1dm
aowDODYve/kCuHfX895ntvL6F2dgyXSjNUYwDn3Qy26vSx5vVL473JWp8mvpyNgr
V+2fM8X5fx/9eu8WO7o7q5KGdhsqedb4fZtjrnXZo1EnOKSrZCQdiMXXAoGBAMC/
9ob/nW5kkLBQqdTCxBR/qlx/RqJTajWUi00iiwYJhErgL4zXgYTwNQjiHJJy3eOV
W2sjl9M9qvBZmmOB6sRzFb9aULBMiOvimQx14opJaUI/u1wJqJ7uMXweTZpXPJi9
zSs5n4qzfgaajXMgRNHITZTsUKL5Sd6njZIA9ezlAoGAF0iFik3xRgMohU139ok4
zVuHEGlqgxIojIE0z2ubM6Le9Rl6Sqh0YwHxZHZhUIrHKCtkP4VWLOc/3VmXIchj
bVy4ISxktUFdyCzepOycsvygQIy5et3jN1ws3F3vEYpJRh1XWJkPxM5hGnbKzJCo
QCNH0eH+zzRqsdakDe+Q/M8CgYBf5aHj3H0ZFVOfRSKZxiUEBdhemLwtus6Wxcbg
o5UDdeypzAwcSIQZ/eCFAOoyOpAG0KJhFZ5N7NqFJi9X3qVNA+0H/Qk0DX/5zA1V
U7lYD9ocqdSvn+aS2/Mmy3TUmx5858GSBeNIgLDs3CwP4TgcH0nqFACydNC5xCb9
QxkXuQKBgQCGt56nS95PYTYlAvxxfrkF0TxLH630CoNJAkVN9PQaLQi34h2uLThE
FntlWvdj9UArt+pPjGRHPhq0DihVqAlJGMH5A0A0sBOl2KeGFHHAh98HIYBxPlhF
QtuhnVhHARQz5qI9N5DkkEE2X/juejBYvQrwuHaFMCzfS6cVRNAoVw==
-----END RSA PRIVATE KEY-----"
        remote.allowAnyHosts = true
        stage("Connect and Deploy") {
            steps {
                sshCommand remote: remote, command: "ls -lrt"
                sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
            }
        }
    }
}