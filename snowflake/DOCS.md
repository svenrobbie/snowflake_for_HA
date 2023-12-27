# Snowflake Proxy for Home Assistant

The Tor Project's Snowflake can now be used on devices running Home Assistant!

This add-on allows you to help people in censored countries access the Internet
without restrictions using [WebRTC](https://en.wikipedia.org/wiki/WebRTC), the
technology that powers the world's most popular real-time communication
software.

You can find a detailed explanation on how Snowflake works on
[The Tor Project's website](https://snowflake.torproject.org).

## Configuration

Example configuration:

```yaml
capacity: 10
nat_retest_interval: 24h
summary_interval: 1h
```

### Option: `capacity`

Defines how many users can connect to your node at the same time. (Default option: `10`)

### Option: `nat_retest_interval`

Defines how often your proxy should test NAT connectivity. `0s` disables this option. (default 24h0m0s)

### Option: `summary_interval`

Defines how often information about your proxy, such as how many people are using your proxy and how much bandwidth they are using, should be shown. (default 1h)

---

#### Time units

As far as time units are concerned, Snowflake is pretty flexible. They must be
declared when defining `nat_retest_interval` and `summary_interval`.

A few valid examples are:

- `24h`
- `12h57m`
- `3600s`
- `1h1m1s`

(... `h` stands for "hours", `m` stands for "minutes" and `s` stands for "seconds")

#### Optional configuration options

A few extra options that are useful for debugging can be found in the
`Configuration` tab. An explanation as to what each setting does can be found
there, but it's best not to touch anything unless if you're...

1. ... experimenting with a test environment like [snowbox](https://github.com/cohosh/snowbox).
2. ... developing this add-on.
3. ... have connection problems / your node is underused.
4. ... have been instructed to do so by a developer.

The most useful option that you will find over there is "Verbose Logs", which
can be helpful if you are having any problems. Other than that, it's best to
leave everything as it is and let Snowflake decide to set the default options
that it finds appropriate, which can vary from update to update.

---

### Additional information

#### Installation

The installation process does not differ from that of other add-ons for Home
Assistant. The add-on is designed to work as soon as you start it.

### License

This add-on is distributed under the [MIT License](LICENSE).

Snowflake, which is not being distributed in this repository, is licensed under
the terms of the
[BSD 3-clause License](https://gitlab.torproject.org/tpo/anti-censorship/pluggable-transports/snowflake/-/blob/main/LICENSE).
