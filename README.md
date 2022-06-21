# Transport FTP

Transport for ApiOpenStudio output to a remote server using the FTP protocol.

# Adding to your project

## Composer

    $ composer require apiopenstudio/transport_ftp

# Configuration

Add a remote output processor to your resource.

The output section example below will return the output in the response as well
as upload the response to a server using FTP:



    output:
        -
            processor: xml_remote
            id: example XML Remote output
            filename: example.xml
            transport: ApiOpenStudio\Plugins\TransportFtp
            parameters:
                host: 192.168.0.1
                root: /home/ftp_user
                username: ftp_user
                password: secret
                port: 21
                ssl: true
                timeout: 90
                utf8: false
                passive: troe
                transferMode: FTP_BINARY
                systemType: unix
                ignorePassiveAddress: true
                timestampsOnUnixListingsEnabled: false
                recurseManually: true
        - 
            response

**Note:** the value for the transport is the full namespace path.

## Parameters

### Required

- host - hostname
- root - root path
- username - username
- password - password

### Optional

- port
- ssl - true|false
- timeout 
- utf8 - true|false
- passive - true|false
- transferMode - PHP constant
- systemType - windows|unix
- ignorePassiveAddress - true|false
- timestampsOnUnixListingsEnabled - true|false
- recurseManually - true|false

# Further information

See [FlySystem documentation][flysystem-docs] and
[The League GitHub][flysystem-github] for more details.

[flysystem-github]: https://github.com/thephpleague/flysystem-ftp

[flysystem-docs]: https://flysystem.thephpleague.com/docs/adapter/ftp/
