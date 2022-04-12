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
        remote.passphrase = "-----BEGIN RSA PRIVATE KEY-----MIIEpAIBAAKCAQEAo3PTPuStWDL9CanO+LJEUQwIHlkw/t7t6VQqCXdSorGgg9/OOfyGJwtXkIrfUXvDXRAgEfrChg2wxEltZHEdCH03zjneoQ4hDkDP4FPe0FJsB4Y6HXfUQRpKZ3S/gebrtmtk3cRetwIr0mtON4xiCMbxmG+MgjEC/r1y316JwRzxln3r8dkV1U7X72hs05F6MKH39rpBO/2cllspucbE1r6BqIIy1QBPap5Y7tYhcemKm5dKbJKUCVZRPO8aehp0RCSzU4oOnZXL3G/+SXIwwQW8OC7f47F7m2VHFxHUQvUTcyKGBR9som7FtPQkT5uNbB3EKTyFT3XSa2ML2H4tUwIDAQABAoIBAQCXxJA9MbAS2SVCt71KBpyQdI+FPmPUA8L8h/2QVI8SKcRVLpYaGXOnBU0FFS1OR5Ca9MISb7f3KPcdCuDcBntiyoHqpqkk+i2PQnbCYJ3e6OkOA4AqpH0dBgBYF3tKbtQmyYkasZ8QZp+x/Zje0yaj57WkSM86g6+4QMhMx0c5Wt4bZ3dGktEeLSFyHaAP9sUs3nzCAC89kzLDhNLjTVm7N08tJr9OYKmvmpPdbbW6WLLSUmEeyQpusutWX1/z75/ssrUDzTBYDcRbi5HEJaxQiroKvEY1KmyNn08Eh3EQWW0vCWigpA4ngNh/inkDvI/JfIbavSKxaZHjrDhhP+rhAoGBANkWuFFq4QElDyGdo0YBzAM3joLptTW+pc96ml+ChHhosbsuV1dmaowDODYve/kCuHfX895ntvL6F2dgyXSjNUYwDn3Qy26vSx5vVL473JWp8mvpyNgrV+2fM8X5fx/9eu8WO7o7q5KGdhsqedb4fZtjrnXZo1EnOKSrZCQdiMXXAoGBAMC/9ob/nW5kkLBQqdTCxBR/qlx/RqJTajWUi00iiwYJhErgL4zXgYTwNQjiHJJy3eOVW2sjl9M9qvBZmmOB6sRzFb9aULBMiOvimQx14opJaUI/u1wJqJ7uMXweTZpXPJi9zSs5n4qzfgaajXMgRNHITZTsUKL5Sd6njZIA9ezlAoGAF0iFik3xRgMohU139ok4zVuHEGlqgxIojIE0z2ubM6Le9Rl6Sqh0YwHxZHZhUIrHKCtkP4VWLOc/3VmXIchjbVy4ISxktUFdyCzepOycsvygQIy5et3jN1ws3F3vEYpJRh1XWJkPxM5hGnbKzJCoQCNH0eH+zzRqsdakDe+Q/M8CgYBf5aHj3H0ZFVOfRSKZxiUEBdhemLwtus6Wxcbgo5UDdeypzAwcSIQZ/eCFAOoyOpAG0KJhFZ5N7NqFJi9X3qVNA+0H/Qk0DX/5zA1VU7lYD9ocqdSvn+aS2/Mmy3TUmx5858GSBeNIgLDs3CwP4TgcH0nqFACydNC5xCb9QxkXuQKBgQCGt56nS95PYTYlAvxxfrkF0TxLH630CoNJAkVN9PQaLQi34h2uLThEFntlWvdj9UArt+pPjGRHPhq0DihVqAlJGMH5A0A0sBOl2KeGFHHAh98HIYBxPlhFQtuhnVhHARQz5qI9N5DkkEE2X/juejBYvQrwuHaFMCzfS6cVRNAoVw==-----END RSA PRIVATE KEY-----"
        remote.allowAnyHosts = true
        stage("Connect and Deploy") {
            steps {
                sshCommand remote: remote, command: "ls -lrt"
                sshCommand remote: remote, command: "for i in {1..5}; do echo -n \"Loop \$i \"; date ; sleep 1; done"
            }
        }
    }
}