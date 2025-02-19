#### Description

People keep trying to trick my players with imitation flags. I want to make sure they get the real thing! I'm going to provide the SHA-256 hash and a decrypt script to help you know that my flags are legitimate.`ssh -p 58311 ctf-player@rhea.picoctf.net`Using the password `6dd28e9b`. Accept the fingerprint with `yes`, and `ls` once connected to begin. Remember, in a shell, passwords are hidden!

- Checksum: 03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8
- To decrypt the file once you've verified the hash, run `./decrypt.sh files/<file>`.

### Hints
1. Checksums let you tell if a file is complete and from the original distributor. If the hash doesn't match, it's a different file.
2. You can create a SHA checksum of a file with `sha256sum <file>` or all files in a directory with `sha256sum <directory>/*`.
3. Remember you can pipe the output of one command to another with `|`. Try practicing with the 'First Grep' challenge if you're stuck!
```bash
ctf-player@pico-chall$ sha256sum  files/* | grep 03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8
03b52eabed517324828b9e09cbbf8a7b0911f348f76cf989ba6d51acede6d5d8  files/00011a60
ctf-player@pico-chall$ ./decrypt.sh files/00011a60
picoCTF{trust_but_verify_00011a60}
```

