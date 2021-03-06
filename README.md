# s3enum

[![Build Status](https://travis-ci.com/koenrh/s3enum.svg?branch=master)](https://travis-ci.com/koenrh/s3enum)

s3enum is a tool to enumerate a target's Amazon S3 buckets. It is fast and leverages
DNS instead of HTTP, which means that requests don't hit AWS directly.

It was originally built back in 2016 to [target GitHub](https://koen.io/2016/02/13/github-bug-bounty-hunting/).

## Installation

```bash
go get -u github.com/koenrh/s3enum
```

## Usage

You need to specify the base name of the target (e.g. `hackerone`), and a word list.
You could either use the `words.txt` file from this repository, or get a word list
[elsewhere](https://github.com/bitquark/dnspop/tree/master/results). Optionally,
you could specify the number of threads (defaults to 10).

```
$ s3enum --wordlist examples/wordlist.txt --suffixlist examples/suffixlist.txt hackerone

hackerone
hackerone-attachment
hackerone-attachments
hackerone-static
hackerone-upload
```
