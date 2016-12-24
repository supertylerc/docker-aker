# aker-docker

You need `docker` installed to use this.  You should build your own
image based on `supertylerc/aker` if you want to use a unique username.

First, copy `aker.ini.sample` to `aker.ini`.  `aker.ini` is in the
`.gitignore`, so you can have it in the repository without risk of
accidentally committing it to the repo.

Next, edit `aker.ini` to reflect your lab environment(s).  It's mostly
self-explanatory, but you should see
[the official Aker documentation][1] for details.

> Note that your `aker.ini` should have the username `lab` unless you
> built a custom container based on `supertylerc/aker`.

You should edit the `docker-compose.yml` as well to include mappings of
names to IP addresses if you used names in your `aker.ini`.

Next, just start the container:

```
docker-compose up -d
```

> If a change isn't picked up that you're expecting to exist, you'll
> need to add the `--build` flag.

Now you can SSH to the server's IP (your laptop or a remote server,
depending on where you deployed the container) on port `2222` as the
user you specified (probably `lab`, the default) and start using `aker`
for all of your labbing needs!

# License

Do whatever you want, but I'm not responsible.

# Author

Tyler Christiansen <code@tylerc.me>

[1]: https://github.com/aker-gateway/Aker/tree/master#installation "Aker Installation"
