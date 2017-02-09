# Go Transmission
Golang lib for Transmission API

### Installation

    $ go get github.com/matthazinski/transmission

### Usage
```go
package main

import (
	"log"

	"github.com/matthazinski/transmission"
)

func main() {
	client, err := transmission.New("http://127.0.0.1:9091/transmission/rpc", "admin", "hunter2")
    if err != nil {
        log.Panic(err)
    }

	torrents, err := client.GetTorrents()
	if err != nil {
		log.Panic(err)
	}

	for _, torrent := range torrents {
		log.Println("Torrent:")
		log.Println("   ID:            ", torrent.ID)
		log.Println("   Name:          ", torrent.Name)
		log.Println("   Status:        ", torrent.Status)
		log.Println("   LeftUntilDone: ", torrent.LeftUntilDone)
		log.Println("   Eta:           ", torrent.Eta)
		log.Println("   UploadRatio:   ", torrent.UploadRatio)
		log.Println("   RateDownload:  ", torrent.RateDownload)
		log.Println("   RateUpload:    ", torrent.RateUpload)
		log.Println("   DownloadDir:   ", torrent.DownloadDir)
		log.Println("   IsFinished:    ", torrent.IsFinished)
		log.Println("   PercentDone:   ", torrent.PercentDone)
		log.Println("   SeedRatioMode: ", torrent.SeedRatioMode)
	}
}
```

### Original author
Long Nguyen (https://github.com/longnguyen11288/go-transmission)
