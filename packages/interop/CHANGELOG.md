# Changelog

## [11.0.0](https://github.com/wforney/helia/compare/interop-v10.1.3...interop-v11.0.0) (2026-03-08)


### ⚠ BREAKING CHANGES

* pass the endpoint URL to the delegated routing router  as a `url` property of an init object
* `ipns.publish` now accepts key name strings rather than private keys Names previously publishing using an user controlled private key, will need to be explicitly published again by first importing the key into the keychain (`await libp2p.keychain.importKey('my-key', key)` and then published with `ipns.publish('my-key', ...)`.
* car.stream has been renamed car.export
* uses libp2p v3 and updated block/data stores
* Fields that would involve DAG traversal have been removed from the output of `fs.stat` - pass the `extended` option to have them returned
* helia now uses libp2p@2.x.x
* requires @helia/interface@4.1.x or later, `resolveDns` has been renamed `resolveDNSLink`
* to support paths in `@helia/ipns`, the return type of `ipns.resolve` is now `{ path: string, cid: CID }` instead of just `CID`
* remove gossipsub from default libp2p services ([#401](https://github.com/wforney/helia/issues/401))
* `helia.routing` is the default routing used, the `libp2p` routing has been removed as it is redundant
* the `libp2p` property has been removed from the `Helia` interface in `@helia/interface` - it is still present on the return type of `createHelia` from the `helia` module
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3, renames `dht` routing to `libp2p`
* uses multiformats v13
* uses multiformats v13 and helia v3
* `helia.pin.add` and `helia.pin.rm` now return `AsyncGenerator<CID>`
* alters the options object passed to the `ipns` factory function
* The libp2p API has changed in a couple of places - please see the [upgrade guide](https://github.com/libp2p/js-libp2p/blob/main/doc/migrations/v0.46-v1.0.0.md)
* the `IPNSRecord` type returned from the `publish` method has changed

### Features

* add @helia/bitswap with sessions ([#409](https://github.com/wforney/helia/issues/409)) ([e582c63](https://github.com/wforney/helia/commit/e582c63ca296c789312f5fcf5e3e18f267f74c03))
* add @helia/http to monorepo ([#372](https://github.com/wforney/helia/issues/372)) ([76220cd](https://github.com/wforney/helia/commit/76220cd5adf45af7fa61fd0a1321de4722b744d6))
* add auto-tls support ([#716](https://github.com/wforney/helia/issues/716)) ([e45e1de](https://github.com/wforney/helia/commit/e45e1dea40120b993f009f8fbb81a9737742196c))
* add ipns reproviding/republishing ([#764](https://github.com/wforney/helia/issues/764)) ([008747b](https://github.com/wforney/helia/commit/008747b59a03682e1b6f648a39635e1b1971e481))
* add libp2p to @helia/http ([#826](https://github.com/wforney/helia/issues/826)) ([235e5c4](https://github.com/wforney/helia/commit/235e5c4093a51bda1e0331f9dd26754f601b582c))
* allow adding peers to session ([#950](https://github.com/wforney/helia/issues/950)) ([33e4681](https://github.com/wforney/helia/commit/33e4681394539d4298a028d2d9ff48a14f76a8e3))
* create @helia/verified-fetch ([#392](https://github.com/wforney/helia/issues/392)) ([f243de2](https://github.com/wforney/helia/commit/f243de26eda64951c2909121730b6a1b8a689bf6))
* export binary from @helia/interop ([#384](https://github.com/wforney/helia/issues/384)) ([3477b27](https://github.com/wforney/helia/commit/3477b2748d44a862e8afeae1a7a2668cdd8a7100))
* expose providers option ([#834](https://github.com/wforney/helia/issues/834)) ([5a911c6](https://github.com/wforney/helia/commit/5a911c6977ec47d1906ccc69b5f57667f22d9ccf))
* GatewayBlockBroker prioritizes & tries all gateways ([#281](https://github.com/wforney/helia/issues/281)) ([9bad21b](https://github.com/wforney/helia/commit/9bad21bd59fe6d1ba4a137db5a46bd2ead5238c3))
* iterable pinning ([#231](https://github.com/wforney/helia/issues/231)) ([c15c774](https://github.com/wforney/helia/commit/c15c7749294d3d4aea5aef70544d088250336798))
* pass initial providers to session ([#777](https://github.com/wforney/helia/issues/777)) ([3d77369](https://github.com/wforney/helia/commit/3d773698389deb70e1a0181eb81fb8b5992857b8))
* rename car stream to export ([#859](https://github.com/wforney/helia/issues/859)) ([63338b9](https://github.com/wforney/helia/commit/63338b9c261a1120592e5afb256dfa8c8feed16b))
* require content-type parser to set content-type ([#423](https://github.com/wforney/helia/issues/423)) ([f58d467](https://github.com/wforney/helia/commit/f58d467108e0b99d1e15b18a899ef81082ad59a7))
* support DNS over HTTPS and DNS-JSON over HTTPS ([#55](https://github.com/wforney/helia/issues/55)) ([2ac0e8b](https://github.com/wforney/helia/commit/2ac0e8b26556b73961e67191c564ac2b18d32b31))
* support paths in @helia/ipns ([#410](https://github.com/wforney/helia/issues/410)) ([ca8d5eb](https://github.com/wforney/helia/commit/ca8d5ebdf587574c7fb84517b558226c3479caa9))
* update helia to v3 and multiformats to v13 ([9f7dc0a](https://github.com/wforney/helia/commit/9f7dc0a0581524531501fc062fefb6ba26d99c02))
* update helia to v3 and multiformats to v13 ([#147](https://github.com/wforney/helia/issues/147)) ([001247c](https://github.com/wforney/helia/commit/001247c6fc38ff3d810736371de901e5e1099f26))
* update helia to v3 and multiformats to v13 ([#167](https://github.com/wforney/helia/issues/167)) ([a0381b9](https://github.com/wforney/helia/commit/a0381b95051bbf3edfa4f53e0ae2d5f43c1e4382))
* update helia to v3 and multiformats to v13 ([#45](https://github.com/wforney/helia/issues/45)) ([f078447](https://github.com/wforney/helia/commit/f078447b6eba4c3d404d62bb930757aa1c0efe74))
* update helia to v3 and multiformats to v13 ([#45](https://github.com/wforney/helia/issues/45)) ([3c7d9d4](https://github.com/wforney/helia/commit/3c7d9d4a8e74e1a808c265fbc6ecbdc24f0f3da9))
* update helia to v3 and multiformats to v13 ([#46](https://github.com/wforney/helia/issues/46)) ([e3dc586](https://github.com/wforney/helia/commit/e3dc5867ffc4de0dd3b05b56eb1b0ce98d50dcb1))
* update helia to v3 and multiformats to v13 ([#52](https://github.com/wforney/helia/issues/52)) ([6405c34](https://github.com/wforney/helia/commit/6405c3487879614dc4dd7308b15c946d644e0488))
* update helia to v3 and multiformats to v13 ([#87](https://github.com/wforney/helia/issues/87)) ([ae7cbc9](https://github.com/wforney/helia/commit/ae7cbc9a16a267cb0f6d7cecd381f919430afaea))
* update to libp2p@v3 and latest data/block stores ([#856](https://github.com/wforney/helia/issues/856)) ([34d3ecd](https://github.com/wforney/helia/commit/34d3ecd76c8424387c57221000e226f08ccd1d1e))
* use custom DNS resolver in @helia/ipns for DNSLink ([#466](https://github.com/wforney/helia/issues/466)) ([2c71b6e](https://github.com/wforney/helia/commit/2c71b6ec8d34dcc722a3914702f67603492c335f)), closes [#369](https://github.com/wforney/helia/issues/369)
* use helia router for IPNS put/get ([#387](https://github.com/wforney/helia/issues/387)) ([ce74026](https://github.com/wforney/helia/commit/ce740268e83f50e6f144b74969a98d54005cd852))


### Bug Fixes

* @helia/* modules validate CID codec ([#643](https://github.com/wforney/helia/issues/643)) ([93aa464](https://github.com/wforney/helia/commit/93aa46459dcff81f0e5eef479f76e39ef5f03736))
* add doc-check script and export types used by functions ([#637](https://github.com/wforney/helia/issues/637)) ([4f14996](https://github.com/wforney/helia/commit/4f14996a9b976f2b60f4c8fe52a4fd1632420749))
* add provider events to bitswap and trustless gateways ([#888](https://github.com/wforney/helia/issues/888)) ([95d95da](https://github.com/wforney/helia/commit/95d95dad7ff2a1e462b5a8a4f57ac40c4503f4ef))
* add sideEffects: false to package.json ([#485](https://github.com/wforney/helia/issues/485)) ([8c45267](https://github.com/wforney/helia/commit/8c45267a474ab10b2faadfebdab33cfe446e8c03))
* allow contentTypeParser with Helia instance ([#427](https://github.com/wforney/helia/issues/427)) ([3283a5c](https://github.com/wforney/helia/commit/3283a5c91ce87894f2b9d7c93126fc74647ba17d))
* convert date to mtime in glob source ([#106](https://github.com/wforney/helia/issues/106)) ([cd9e903](https://github.com/wforney/helia/commit/cd9e903c2ccac61372eaa64a61b4a8f3d79f9d4a))
* create @helia/block-brokers package ([#341](https://github.com/wforney/helia/issues/341)) ([#342](https://github.com/wforney/helia/issues/342)) ([2979147](https://github.com/wforney/helia/commit/297914756fa06dc0c28890a2654d1159d16689c2))
* do not depend on external domains in dnslink tests ([#547](https://github.com/wforney/helia/issues/547)) ([21ef20c](https://github.com/wforney/helia/commit/21ef20cd05e4d0231d0e3d7d2cfbd21fb75b78a2))
* emit provider event for initial providers ([#953](https://github.com/wforney/helia/issues/953)) ([f058fba](https://github.com/wforney/helia/commit/f058fba8a06f8afdd3558bdf7c3801381648ffec))
* emit provider event for initial provides ([f058fba](https://github.com/wforney/helia/commit/f058fba8a06f8afdd3558bdf7c3801381648ffec))
* enforce maximum identity hash size ([#865](https://github.com/wforney/helia/issues/865)) ([d9051cd](https://github.com/wforney/helia/commit/d9051cdc2fd19ab7def32d195b5798b27d85a078)), closes [#846](https://github.com/wforney/helia/issues/846)
* include aegir config in interop and run from install dir ([#389](https://github.com/wforney/helia/issues/389)) ([a2229bd](https://github.com/wforney/helia/commit/a2229bd79d5c8b805604bb24bad222462a9ed8cc))
* **kubo:** ⬆️ Upgrading go-ipfs to kubo ([#251](https://github.com/wforney/helia/issues/251)) ([963a7a2](https://github.com/wforney/helia/commit/963a7a21774703a105c865a5b6db670f278eec73))
* remove gossipsub from default libp2p services ([#401](https://github.com/wforney/helia/issues/401)) ([99c94f4](https://github.com/wforney/helia/commit/99c94f4b85c4ed826a6195207e3545cbbc87a6d1))
* return simple stats or extended stats ([#760](https://github.com/wforney/helia/issues/760)) ([325b36f](https://github.com/wforney/helia/commit/325b36f70624d3dcc25b2723f9e3e2d26e1e5199))
* support multiple DNSLink entries ([#863](https://github.com/wforney/helia/issues/863)) ([fe38409](https://github.com/wforney/helia/commit/fe384098a0930915eff4c41d562606955e0e710d)), closes [#368](https://github.com/wforney/helia/issues/368)
* test for subscribers to ipns pubsub topic ([#584](https://github.com/wforney/helia/issues/584)) ([c9c644c](https://github.com/wforney/helia/commit/c9c644c11657ec1411b3f04933fa62501151f732))
* update ipns module to v9 and fix double verification of records ([#396](https://github.com/wforney/helia/issues/396)) ([f2853f8](https://github.com/wforney/helia/commit/f2853f8bd5bdcee8ab7a685355b0be47f29620e0))
* update js-libp2p types ([#570](https://github.com/wforney/helia/issues/570)) ([b4877b5](https://github.com/wforney/helia/commit/b4877b5b768895684be90a26f4303ae65fc209e7))
* update project deps and docs ([77e34fc](https://github.com/wforney/helia/commit/77e34fc115cbfb82585fd954bcf389ecebf655bc))
* update to libp2p@2.x.x ([#630](https://github.com/wforney/helia/issues/630)) ([ec8bf66](https://github.com/wforney/helia/commit/ec8bf66dd870b42d6e5ef2b41706102397e0d39a))
* update type import path ([#379](https://github.com/wforney/helia/issues/379)) ([ece384a](https://github.com/wforney/helia/commit/ece384aab5e1c95857aa4aa07b86656710d8ca35))
* use bytestream methods to add byte streams ([#758](https://github.com/wforney/helia/issues/758)) ([70b8fa9](https://github.com/wforney/helia/commit/70b8fa96cb5fe0fddbb0e1528e6685778af90aa8))
* use hasCode from multiformats ([#635](https://github.com/wforney/helia/issues/635)) ([f5a03fc](https://github.com/wforney/helia/commit/f5a03fc28d0cd59841b842306f912c092aeabd5f))
* use libp2p provider routing field ([#889](https://github.com/wforney/helia/issues/889)) ([d4d97b8](https://github.com/wforney/helia/commit/d4d97b83f76be7e3b480052467408839f808e230))
* use non-deprecated factory function to create delegated client ([#934](https://github.com/wforney/helia/issues/934)) ([20ba9cf](https://github.com/wforney/helia/commit/20ba9cf6256961d2b664af0e8f48b5e9d009d834))
* use unixfs exporter to traverse DAGs ([#455](https://github.com/wforney/helia/issues/455)) ([6f8c15b](https://github.com/wforney/helia/commit/6f8c15b769c08bf73e7c62dab79909b5ecfc3c93))


### Documentation

* add spell checker to ci ([#743](https://github.com/wforney/helia/issues/743)) ([45ca6bc](https://github.com/wforney/helia/commit/45ca6bc70b1644028500101044595fa0e2199b07))
* fix grammar - it's -&gt; its ([#565](https://github.com/wforney/helia/issues/565)) ([155e24d](https://github.com/wforney/helia/commit/155e24db8c06c33972895d702a656e0c2996f3d9))
* update generated docs to include version in module names ([#296](https://github.com/wforney/helia/issues/296)) ([0776106](https://github.com/wforney/helia/commit/0776106710d6641ac82b446f7fde6c40d788a0b4))


### Dependencies

* bump @chainsafe/libp2p-gossipsub from 11.2.1 to 12.0.0 ([#430](https://github.com/wforney/helia/issues/430)) ([9b1ddf8](https://github.com/wforney/helia/commit/9b1ddf85e503ecf5c3ddaa04826bef2f75454b44))
* bump @chainsafe/libp2p-gossipsub from 12.0.0 to 13.0.0 ([#457](https://github.com/wforney/helia/issues/457)) ([cb35a1b](https://github.com/wforney/helia/commit/cb35a1ba149628181b3bb48e14d927d2ebc9c23b))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#2](https://github.com/wforney/helia/issues/2)) ([351fae7](https://github.com/wforney/helia/commit/351fae7a129e642a6f312c9a61609273dec190bf))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#30](https://github.com/wforney/helia/issues/30)) ([aa6ebcf](https://github.com/wforney/helia/commit/aa6ebcf9f58eebf842113985adee4710b009562d))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#32](https://github.com/wforney/helia/issues/32)) ([68656a8](https://github.com/wforney/helia/commit/68656a81b7cd1238641a41573915635905e4a6ed))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#32](https://github.com/wforney/helia/issues/32)) ([eb836ef](https://github.com/wforney/helia/commit/eb836ef15f6bc754fbab4fdbe47c76f5492a56d9))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#34](https://github.com/wforney/helia/issues/34)) ([d48f2c5](https://github.com/wforney/helia/commit/d48f2c58338af0d096a1f855ab85a621fce1cc01))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#39](https://github.com/wforney/helia/issues/39)) ([7c9bc2e](https://github.com/wforney/helia/commit/7c9bc2e9f99ccbaec1d8c25c900585deb5f6a327))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#87](https://github.com/wforney/helia/issues/87)) ([098a305](https://github.com/wforney/helia/commit/098a305241024ed3903b686892ded8abfca55f5f))
* bump aegir from 42.2.11 to 43.0.1 ([#552](https://github.com/wforney/helia/issues/552)) ([74ccc92](https://github.com/wforney/helia/commit/74ccc92793a6d0bb4bee714d9fe4fa4183aa4ee8))
* bump aegir from 43.0.3 to 44.0.1 ([#569](https://github.com/wforney/helia/issues/569)) ([6952f05](https://github.com/wforney/helia/commit/6952f05357844e5aa3dffb2afaf261df06b9b7c1))
* bump aegir from 44.1.4 to 45.0.1 ([#669](https://github.com/wforney/helia/issues/669)) ([e58e49c](https://github.com/wforney/helia/commit/e58e49c6aed8ea9d1e9851435a25e33fdbee3781))
* bump ipfsd-ctl from 13.0.0 to 14.0.0 ([#505](https://github.com/wforney/helia/issues/505)) ([97fb1a7](https://github.com/wforney/helia/commit/97fb1a78a2e585a66861a2d0fdc4eabf8b28bd04))
* bump kubo from 0.25.0 to 0.26.0 ([#400](https://github.com/wforney/helia/issues/400)) ([a9c55f0](https://github.com/wforney/helia/commit/a9c55f0e672e439cbcc6b938963ab150997c6e45))
* bump kubo from 0.26.0 to 0.27.0 ([#461](https://github.com/wforney/helia/issues/461)) ([c69913c](https://github.com/wforney/helia/commit/c69913c546f2bb74344f804f25a93f23adeb9b49))
* bump kubo from 0.28.0 to 0.29.0 ([#555](https://github.com/wforney/helia/issues/555)) ([117198f](https://github.com/wforney/helia/commit/117198f85511bfe339b96b588cd62015ed6e69a4))
* bump kubo from 0.30.0 to 0.31.0 ([#656](https://github.com/wforney/helia/issues/656)) ([8364296](https://github.com/wforney/helia/commit/83642961c7c6417e58229226048d69a642edcfff))
* bump kubo from 0.31.0 to 0.32.0 ([#679](https://github.com/wforney/helia/issues/679)) ([c09fef2](https://github.com/wforney/helia/commit/c09fef29b749eecf969f9812dea7ab49477582f7))
* bump kubo from 0.34.1 to 0.35.0 in the kubo-deps group ([#806](https://github.com/wforney/helia/issues/806)) ([50a9766](https://github.com/wforney/helia/commit/50a9766297d9a55678c4ab785960b9fa9768715b))
* bump kubo from 0.38.2 to 0.39.0 in the kubo-deps group ([#911](https://github.com/wforney/helia/issues/911)) ([5e06685](https://github.com/wforney/helia/commit/5e0668547b3029ce6ab9fd70081bce70aea950fb))
* bump kubo from 0.39.0 to 0.40.0 ([#963](https://github.com/wforney/helia/issues/963)) ([2d30414](https://github.com/wforney/helia/commit/2d30414a0752c64428a68ef3e15695eb8506b163))
* bump multiformats from 11.0.2 to 12.0.1 ([#4](https://github.com/wforney/helia/issues/4)) ([50bed0f](https://github.com/wforney/helia/commit/50bed0f32b3c07111de804b0e6471e36d8e66626))
* bump multiformats from 11.0.2 to 12.0.1 ([#8](https://github.com/wforney/helia/issues/8)) ([c2a2ee3](https://github.com/wforney/helia/commit/c2a2ee38cc8fa76c8a6d0c92c44023c148148a7e))
* bump multiformats from 11.0.2 to 12.0.1 ([#8](https://github.com/wforney/helia/issues/8)) ([c89b8f1](https://github.com/wforney/helia/commit/c89b8f12d700f0e23dc574cc32f7726d9c9558de))
* bump multiformats from 12.1.3 to 13.0.0 ([#354](https://github.com/wforney/helia/issues/354)) ([1d16bf8](https://github.com/wforney/helia/commit/1d16bf89acd10ac79baf53f0cbc5f92d0e9d8301))
* bump the kubo-deps group across 7 directories with 1 update ([#734](https://github.com/wforney/helia/issues/734)) ([f7155d8](https://github.com/wforney/helia/commit/f7155d8bece43dd91d19060881294f61df9d222c))
* bump the kubo-deps group with 2 updates ([#867](https://github.com/wforney/helia/issues/867)) ([c442439](https://github.com/wforney/helia/commit/c4424392b6d00bf7b144a15f1125990b7388b2b7))
* **dev:** bump @libp2p/websockets from 6.0.3 to 7.0.5 ([#35](https://github.com/wforney/helia/issues/35)) ([de04834](https://github.com/wforney/helia/commit/de048348666a7961cda517ce26f8aedfa987a3bc))
* **dev:** bump @libp2p/websockets from 6.0.3 to 7.0.5 ([#36](https://github.com/wforney/helia/issues/36)) ([5f4169e](https://github.com/wforney/helia/commit/5f4169e9ddb16a7d026db395ad3e9c1a2f764bb7))
* **dev:** bump @multiformats/sha3 from 2.0.17 to 3.0.0 ([#249](https://github.com/wforney/helia/issues/249)) ([7f2dcf8](https://github.com/wforney/helia/commit/7f2dcf8b878f80e75b3d0dc5a3c49caeb0430785))
* **dev:** bump aegir from 39.0.13 to 40.0.11 ([#26](https://github.com/wforney/helia/issues/26)) ([37b6ba1](https://github.com/wforney/helia/commit/37b6ba14e085073b966fced3c3777519601d0a81))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#105](https://github.com/wforney/helia/issues/105)) ([2421ee2](https://github.com/wforney/helia/commit/2421ee2b4440446160e1a665bc5ecfc92d2b64de))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#107](https://github.com/wforney/helia/issues/107)) ([5402d30](https://github.com/wforney/helia/commit/5402d30de1437052e9e9b955d9be3c2898515447))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#273](https://github.com/wforney/helia/issues/273)) ([9a9f637](https://github.com/wforney/helia/commit/9a9f63787223eff7eae3b72e59b79b11baa621ea))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#36](https://github.com/wforney/helia/issues/36)) ([ca3f05a](https://github.com/wforney/helia/commit/ca3f05a74316f53b0e44f5edd6e303b6e8463bf2))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#36](https://github.com/wforney/helia/issues/36)) ([9f57d11](https://github.com/wforney/helia/commit/9f57d11e461a3b1fddbc2a92e225d31eee56613c))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#36](https://github.com/wforney/helia/issues/36)) ([77e29bc](https://github.com/wforney/helia/commit/77e29bcdda33387b8bf15124bc316ef03b434433))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#41](https://github.com/wforney/helia/issues/41)) ([e8fc99f](https://github.com/wforney/helia/commit/e8fc99f4e372eaf72c2598f5a7a9942143c6d788))
* **dev:** bump go-ipfs from 0.20.0 to 0.22.0 ([#22](https://github.com/wforney/helia/issues/22)) ([c8a2e7f](https://github.com/wforney/helia/commit/c8a2e7ff11df35b6c7e4e3d336890e5d9f5f51fb))
* **dev:** bump go-ipfs from 0.20.0 to 0.22.0 ([#24](https://github.com/wforney/helia/issues/24)) ([cff694f](https://github.com/wforney/helia/commit/cff694f6bc88b25e71d3243b045c65932bfa9874))
* **dev:** bump go-ipfs from 0.20.0 to 0.22.0 ([#81](https://github.com/wforney/helia/issues/81)) ([15fb863](https://github.com/wforney/helia/commit/15fb86380bff97b54120009fb20a0dc5bfa4cc92))
* **dev:** bump helia from 2.0.1 to 2.0.3 ([#10](https://github.com/wforney/helia/issues/10)) ([6911470](https://github.com/wforney/helia/commit/6911470cb43720798fca571669a166eb3689dad2))
* **dev:** bump kubo from 0.22.0 to 0.23.0 ([#278](https://github.com/wforney/helia/issues/278)) ([51316ba](https://github.com/wforney/helia/commit/51316baa71ec22b91013a7f98b46f5ad420b984a))
* **dev:** bump kubo from 0.24.0 to 0.25.0 ([#351](https://github.com/wforney/helia/issues/351)) ([9efe50d](https://github.com/wforney/helia/commit/9efe50df7f130c062f42b0a391bdb1f1e7e50af8))
* **dev:** bump libp2p from 0.45.9 to 0.46.6 ([#92](https://github.com/wforney/helia/issues/92)) ([efe02e5](https://github.com/wforney/helia/commit/efe02e5b38992189edb40cd34d79e76dca4c34a3))
* go-ipfs -&gt; kubo ([#53](https://github.com/wforney/helia/issues/53)) ([f13daae](https://github.com/wforney/helia/commit/f13daae3d62579b0b181bc5387c5d7b8e10029a5))
* update aegir to 47.x.x ([#804](https://github.com/wforney/helia/issues/804)) ([60fbbc2](https://github.com/wforney/helia/commit/60fbbc2eb08e023e2eac02ae0e89ed143d715084))
* update all deps ([#792](https://github.com/wforney/helia/issues/792)) ([d43efc7](https://github.com/wforney/helia/commit/d43efc7bdfff34071a8e4e22e01f659fbac0b78e))
* update delegated routing client ([#937](https://github.com/wforney/helia/issues/937)) ([1c79dae](https://github.com/wforney/helia/commit/1c79dae55273a2751eb6d11648702f2946df4bcc))
* update ipns to v7.x.x ([#106](https://github.com/wforney/helia/issues/106)) ([83a1d14](https://github.com/wforney/helia/commit/83a1d147e8ba758efd7d2574ea486218bd1f3df2))
* update kad-dht to 14.0.0 ([#648](https://github.com/wforney/helia/issues/648)) ([60d8c8a](https://github.com/wforney/helia/commit/60d8c8a9ff2104302d1c87bcf39258f1da33cd45))
* update libp2p patch versions ([917a1bc](https://github.com/wforney/helia/commit/917a1bceb9e9b56428a15dc3377a963f06affd12))
* updates to libp2p v1 ([#320](https://github.com/wforney/helia/issues/320)) ([635d7a2](https://github.com/wforney/helia/commit/635d7a2938111ccc53f8defbd9b8f8f8ea3e8e6a))
## [11.0.0](https://github.com/wforney/helia/compare/interop-v10.1.3...interop-v11.0.0) (2026-03-08)


### ⚠ BREAKING CHANGES

* pass the endpoint URL to the delegated routing router  as a `url` property of an init object
* `ipns.publish` now accepts key name strings rather than private keys Names previously publishing using an user controlled private key, will need to be explicitly published again by first importing the key into the keychain (`await libp2p.keychain.importKey('my-key', key)` and then published with `ipns.publish('my-key', ...)`.
* car.stream has been renamed car.export
* uses libp2p v3 and updated block/data stores
* Fields that would involve DAG traversal have been removed from the output of `fs.stat` - pass the `extended` option to have them returned
* helia now uses libp2p@2.x.x
* requires @helia/interface@4.1.x or later, `resolveDns` has been renamed `resolveDNSLink`
* to support paths in `@helia/ipns`, the return type of `ipns.resolve` is now `{ path: string, cid: CID }` instead of just `CID`
* remove gossipsub from default libp2p services ([#401](https://github.com/wforney/helia/issues/401))
* `helia.routing` is the default routing used, the `libp2p` routing has been removed as it is redundant
* the `libp2p` property has been removed from the `Helia` interface in `@helia/interface` - it is still present on the return type of `createHelia` from the `helia` module
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3, renames `dht` routing to `libp2p`
* uses multiformats v13
* uses multiformats v13 and helia v3
* `helia.pin.add` and `helia.pin.rm` now return `AsyncGenerator<CID>`
* alters the options object passed to the `ipns` factory function
* The libp2p API has changed in a couple of places - please see the [upgrade guide](https://github.com/libp2p/js-libp2p/blob/main/doc/migrations/v0.46-v1.0.0.md)
* the `IPNSRecord` type returned from the `publish` method has changed

### Features

* add @helia/bitswap with sessions ([#409](https://github.com/wforney/helia/issues/409)) ([e582c63](https://github.com/wforney/helia/commit/e582c63ca296c789312f5fcf5e3e18f267f74c03))
* add @helia/http to monorepo ([#372](https://github.com/wforney/helia/issues/372)) ([76220cd](https://github.com/wforney/helia/commit/76220cd5adf45af7fa61fd0a1321de4722b744d6))
* add auto-tls support ([#716](https://github.com/wforney/helia/issues/716)) ([e45e1de](https://github.com/wforney/helia/commit/e45e1dea40120b993f009f8fbb81a9737742196c))
* add ipns reproviding/republishing ([#764](https://github.com/wforney/helia/issues/764)) ([008747b](https://github.com/wforney/helia/commit/008747b59a03682e1b6f648a39635e1b1971e481))
* add libp2p to @helia/http ([#826](https://github.com/wforney/helia/issues/826)) ([235e5c4](https://github.com/wforney/helia/commit/235e5c4093a51bda1e0331f9dd26754f601b582c))
* allow adding peers to session ([#950](https://github.com/wforney/helia/issues/950)) ([33e4681](https://github.com/wforney/helia/commit/33e4681394539d4298a028d2d9ff48a14f76a8e3))
* create @helia/verified-fetch ([#392](https://github.com/wforney/helia/issues/392)) ([f243de2](https://github.com/wforney/helia/commit/f243de26eda64951c2909121730b6a1b8a689bf6))
* export binary from @helia/interop ([#384](https://github.com/wforney/helia/issues/384)) ([3477b27](https://github.com/wforney/helia/commit/3477b2748d44a862e8afeae1a7a2668cdd8a7100))
* expose providers option ([#834](https://github.com/wforney/helia/issues/834)) ([5a911c6](https://github.com/wforney/helia/commit/5a911c6977ec47d1906ccc69b5f57667f22d9ccf))
* GatewayBlockBroker prioritizes & tries all gateways ([#281](https://github.com/wforney/helia/issues/281)) ([9bad21b](https://github.com/wforney/helia/commit/9bad21bd59fe6d1ba4a137db5a46bd2ead5238c3))
* iterable pinning ([#231](https://github.com/wforney/helia/issues/231)) ([c15c774](https://github.com/wforney/helia/commit/c15c7749294d3d4aea5aef70544d088250336798))
* pass initial providers to session ([#777](https://github.com/wforney/helia/issues/777)) ([3d77369](https://github.com/wforney/helia/commit/3d773698389deb70e1a0181eb81fb8b5992857b8))
* rename car stream to export ([#859](https://github.com/wforney/helia/issues/859)) ([63338b9](https://github.com/wforney/helia/commit/63338b9c261a1120592e5afb256dfa8c8feed16b))
* require content-type parser to set content-type ([#423](https://github.com/wforney/helia/issues/423)) ([f58d467](https://github.com/wforney/helia/commit/f58d467108e0b99d1e15b18a899ef81082ad59a7))
* support DNS over HTTPS and DNS-JSON over HTTPS ([#55](https://github.com/wforney/helia/issues/55)) ([2ac0e8b](https://github.com/wforney/helia/commit/2ac0e8b26556b73961e67191c564ac2b18d32b31))
* support paths in @helia/ipns ([#410](https://github.com/wforney/helia/issues/410)) ([ca8d5eb](https://github.com/wforney/helia/commit/ca8d5ebdf587574c7fb84517b558226c3479caa9))
* update helia to v3 and multiformats to v13 ([9f7dc0a](https://github.com/wforney/helia/commit/9f7dc0a0581524531501fc062fefb6ba26d99c02))
* update helia to v3 and multiformats to v13 ([#147](https://github.com/wforney/helia/issues/147)) ([001247c](https://github.com/wforney/helia/commit/001247c6fc38ff3d810736371de901e5e1099f26))
* update helia to v3 and multiformats to v13 ([#167](https://github.com/wforney/helia/issues/167)) ([a0381b9](https://github.com/wforney/helia/commit/a0381b95051bbf3edfa4f53e0ae2d5f43c1e4382))
* update helia to v3 and multiformats to v13 ([#45](https://github.com/wforney/helia/issues/45)) ([f078447](https://github.com/wforney/helia/commit/f078447b6eba4c3d404d62bb930757aa1c0efe74))
* update helia to v3 and multiformats to v13 ([#45](https://github.com/wforney/helia/issues/45)) ([3c7d9d4](https://github.com/wforney/helia/commit/3c7d9d4a8e74e1a808c265fbc6ecbdc24f0f3da9))
* update helia to v3 and multiformats to v13 ([#46](https://github.com/wforney/helia/issues/46)) ([e3dc586](https://github.com/wforney/helia/commit/e3dc5867ffc4de0dd3b05b56eb1b0ce98d50dcb1))
* update helia to v3 and multiformats to v13 ([#52](https://github.com/wforney/helia/issues/52)) ([6405c34](https://github.com/wforney/helia/commit/6405c3487879614dc4dd7308b15c946d644e0488))
* update helia to v3 and multiformats to v13 ([#87](https://github.com/wforney/helia/issues/87)) ([ae7cbc9](https://github.com/wforney/helia/commit/ae7cbc9a16a267cb0f6d7cecd381f919430afaea))
* update to libp2p@v3 and latest data/block stores ([#856](https://github.com/wforney/helia/issues/856)) ([34d3ecd](https://github.com/wforney/helia/commit/34d3ecd76c8424387c57221000e226f08ccd1d1e))
* use custom DNS resolver in @helia/ipns for DNSLink ([#466](https://github.com/wforney/helia/issues/466)) ([2c71b6e](https://github.com/wforney/helia/commit/2c71b6ec8d34dcc722a3914702f67603492c335f)), closes [#369](https://github.com/wforney/helia/issues/369)
* use helia router for IPNS put/get ([#387](https://github.com/wforney/helia/issues/387)) ([ce74026](https://github.com/wforney/helia/commit/ce740268e83f50e6f144b74969a98d54005cd852))


### Bug Fixes

* @helia/* modules validate CID codec ([#643](https://github.com/wforney/helia/issues/643)) ([93aa464](https://github.com/wforney/helia/commit/93aa46459dcff81f0e5eef479f76e39ef5f03736))
* add doc-check script and export types used by functions ([#637](https://github.com/wforney/helia/issues/637)) ([4f14996](https://github.com/wforney/helia/commit/4f14996a9b976f2b60f4c8fe52a4fd1632420749))
* add provider events to bitswap and trustless gateways ([#888](https://github.com/wforney/helia/issues/888)) ([95d95da](https://github.com/wforney/helia/commit/95d95dad7ff2a1e462b5a8a4f57ac40c4503f4ef))
* add sideEffects: false to package.json ([#485](https://github.com/wforney/helia/issues/485)) ([8c45267](https://github.com/wforney/helia/commit/8c45267a474ab10b2faadfebdab33cfe446e8c03))
* allow contentTypeParser with Helia instance ([#427](https://github.com/wforney/helia/issues/427)) ([3283a5c](https://github.com/wforney/helia/commit/3283a5c91ce87894f2b9d7c93126fc74647ba17d))
* convert date to mtime in glob source ([#106](https://github.com/wforney/helia/issues/106)) ([cd9e903](https://github.com/wforney/helia/commit/cd9e903c2ccac61372eaa64a61b4a8f3d79f9d4a))
* create @helia/block-brokers package ([#341](https://github.com/wforney/helia/issues/341)) ([#342](https://github.com/wforney/helia/issues/342)) ([2979147](https://github.com/wforney/helia/commit/297914756fa06dc0c28890a2654d1159d16689c2))
* do not depend on external domains in dnslink tests ([#547](https://github.com/wforney/helia/issues/547)) ([21ef20c](https://github.com/wforney/helia/commit/21ef20cd05e4d0231d0e3d7d2cfbd21fb75b78a2))
* emit provider event for initial providers ([#953](https://github.com/wforney/helia/issues/953)) ([f058fba](https://github.com/wforney/helia/commit/f058fba8a06f8afdd3558bdf7c3801381648ffec))
* emit provider event for initial provides ([f058fba](https://github.com/wforney/helia/commit/f058fba8a06f8afdd3558bdf7c3801381648ffec))
* enforce maximum identity hash size ([#865](https://github.com/wforney/helia/issues/865)) ([d9051cd](https://github.com/wforney/helia/commit/d9051cdc2fd19ab7def32d195b5798b27d85a078)), closes [#846](https://github.com/wforney/helia/issues/846)
* include aegir config in interop and run from install dir ([#389](https://github.com/wforney/helia/issues/389)) ([a2229bd](https://github.com/wforney/helia/commit/a2229bd79d5c8b805604bb24bad222462a9ed8cc))
* **kubo:** ⬆️ Upgrading go-ipfs to kubo ([#251](https://github.com/wforney/helia/issues/251)) ([963a7a2](https://github.com/wforney/helia/commit/963a7a21774703a105c865a5b6db670f278eec73))
* remove gossipsub from default libp2p services ([#401](https://github.com/wforney/helia/issues/401)) ([99c94f4](https://github.com/wforney/helia/commit/99c94f4b85c4ed826a6195207e3545cbbc87a6d1))
* return simple stats or extended stats ([#760](https://github.com/wforney/helia/issues/760)) ([325b36f](https://github.com/wforney/helia/commit/325b36f70624d3dcc25b2723f9e3e2d26e1e5199))
* support multiple DNSLink entries ([#863](https://github.com/wforney/helia/issues/863)) ([fe38409](https://github.com/wforney/helia/commit/fe384098a0930915eff4c41d562606955e0e710d)), closes [#368](https://github.com/wforney/helia/issues/368)
* test for subscribers to ipns pubsub topic ([#584](https://github.com/wforney/helia/issues/584)) ([c9c644c](https://github.com/wforney/helia/commit/c9c644c11657ec1411b3f04933fa62501151f732))
* update ipns module to v9 and fix double verification of records ([#396](https://github.com/wforney/helia/issues/396)) ([f2853f8](https://github.com/wforney/helia/commit/f2853f8bd5bdcee8ab7a685355b0be47f29620e0))
* update js-libp2p types ([#570](https://github.com/wforney/helia/issues/570)) ([b4877b5](https://github.com/wforney/helia/commit/b4877b5b768895684be90a26f4303ae65fc209e7))
* update project deps and docs ([77e34fc](https://github.com/wforney/helia/commit/77e34fc115cbfb82585fd954bcf389ecebf655bc))
* update to libp2p@2.x.x ([#630](https://github.com/wforney/helia/issues/630)) ([ec8bf66](https://github.com/wforney/helia/commit/ec8bf66dd870b42d6e5ef2b41706102397e0d39a))
* update type import path ([#379](https://github.com/wforney/helia/issues/379)) ([ece384a](https://github.com/wforney/helia/commit/ece384aab5e1c95857aa4aa07b86656710d8ca35))
* use bytestream methods to add byte streams ([#758](https://github.com/wforney/helia/issues/758)) ([70b8fa9](https://github.com/wforney/helia/commit/70b8fa96cb5fe0fddbb0e1528e6685778af90aa8))
* use hasCode from multiformats ([#635](https://github.com/wforney/helia/issues/635)) ([f5a03fc](https://github.com/wforney/helia/commit/f5a03fc28d0cd59841b842306f912c092aeabd5f))
* use libp2p provider routing field ([#889](https://github.com/wforney/helia/issues/889)) ([d4d97b8](https://github.com/wforney/helia/commit/d4d97b83f76be7e3b480052467408839f808e230))
* use non-deprecated factory function to create delegated client ([#934](https://github.com/wforney/helia/issues/934)) ([20ba9cf](https://github.com/wforney/helia/commit/20ba9cf6256961d2b664af0e8f48b5e9d009d834))
* use unixfs exporter to traverse DAGs ([#455](https://github.com/wforney/helia/issues/455)) ([6f8c15b](https://github.com/wforney/helia/commit/6f8c15b769c08bf73e7c62dab79909b5ecfc3c93))


### Documentation

* add spell checker to ci ([#743](https://github.com/wforney/helia/issues/743)) ([45ca6bc](https://github.com/wforney/helia/commit/45ca6bc70b1644028500101044595fa0e2199b07))
* fix grammar - it's -&gt; its ([#565](https://github.com/wforney/helia/issues/565)) ([155e24d](https://github.com/wforney/helia/commit/155e24db8c06c33972895d702a656e0c2996f3d9))
* update generated docs to include version in module names ([#296](https://github.com/wforney/helia/issues/296)) ([0776106](https://github.com/wforney/helia/commit/0776106710d6641ac82b446f7fde6c40d788a0b4))


### Dependencies

* bump @chainsafe/libp2p-gossipsub from 11.2.1 to 12.0.0 ([#430](https://github.com/wforney/helia/issues/430)) ([9b1ddf8](https://github.com/wforney/helia/commit/9b1ddf85e503ecf5c3ddaa04826bef2f75454b44))
* bump @chainsafe/libp2p-gossipsub from 12.0.0 to 13.0.0 ([#457](https://github.com/wforney/helia/issues/457)) ([cb35a1b](https://github.com/wforney/helia/commit/cb35a1ba149628181b3bb48e14d927d2ebc9c23b))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#2](https://github.com/wforney/helia/issues/2)) ([351fae7](https://github.com/wforney/helia/commit/351fae7a129e642a6f312c9a61609273dec190bf))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#30](https://github.com/wforney/helia/issues/30)) ([aa6ebcf](https://github.com/wforney/helia/commit/aa6ebcf9f58eebf842113985adee4710b009562d))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#32](https://github.com/wforney/helia/issues/32)) ([68656a8](https://github.com/wforney/helia/commit/68656a81b7cd1238641a41573915635905e4a6ed))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#32](https://github.com/wforney/helia/issues/32)) ([eb836ef](https://github.com/wforney/helia/commit/eb836ef15f6bc754fbab4fdbe47c76f5492a56d9))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#34](https://github.com/wforney/helia/issues/34)) ([d48f2c5](https://github.com/wforney/helia/commit/d48f2c58338af0d096a1f855ab85a621fce1cc01))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#39](https://github.com/wforney/helia/issues/39)) ([7c9bc2e](https://github.com/wforney/helia/commit/7c9bc2e9f99ccbaec1d8c25c900585deb5f6a327))
* bump @helia/interface from 1.2.2 to 2.0.0 ([#87](https://github.com/wforney/helia/issues/87)) ([098a305](https://github.com/wforney/helia/commit/098a305241024ed3903b686892ded8abfca55f5f))
* bump aegir from 42.2.11 to 43.0.1 ([#552](https://github.com/wforney/helia/issues/552)) ([74ccc92](https://github.com/wforney/helia/commit/74ccc92793a6d0bb4bee714d9fe4fa4183aa4ee8))
* bump aegir from 43.0.3 to 44.0.1 ([#569](https://github.com/wforney/helia/issues/569)) ([6952f05](https://github.com/wforney/helia/commit/6952f05357844e5aa3dffb2afaf261df06b9b7c1))
* bump aegir from 44.1.4 to 45.0.1 ([#669](https://github.com/wforney/helia/issues/669)) ([e58e49c](https://github.com/wforney/helia/commit/e58e49c6aed8ea9d1e9851435a25e33fdbee3781))
* bump ipfsd-ctl from 13.0.0 to 14.0.0 ([#505](https://github.com/wforney/helia/issues/505)) ([97fb1a7](https://github.com/wforney/helia/commit/97fb1a78a2e585a66861a2d0fdc4eabf8b28bd04))
* bump kubo from 0.25.0 to 0.26.0 ([#400](https://github.com/wforney/helia/issues/400)) ([a9c55f0](https://github.com/wforney/helia/commit/a9c55f0e672e439cbcc6b938963ab150997c6e45))
* bump kubo from 0.26.0 to 0.27.0 ([#461](https://github.com/wforney/helia/issues/461)) ([c69913c](https://github.com/wforney/helia/commit/c69913c546f2bb74344f804f25a93f23adeb9b49))
* bump kubo from 0.28.0 to 0.29.0 ([#555](https://github.com/wforney/helia/issues/555)) ([117198f](https://github.com/wforney/helia/commit/117198f85511bfe339b96b588cd62015ed6e69a4))
* bump kubo from 0.30.0 to 0.31.0 ([#656](https://github.com/wforney/helia/issues/656)) ([8364296](https://github.com/wforney/helia/commit/83642961c7c6417e58229226048d69a642edcfff))
* bump kubo from 0.31.0 to 0.32.0 ([#679](https://github.com/wforney/helia/issues/679)) ([c09fef2](https://github.com/wforney/helia/commit/c09fef29b749eecf969f9812dea7ab49477582f7))
* bump kubo from 0.34.1 to 0.35.0 in the kubo-deps group ([#806](https://github.com/wforney/helia/issues/806)) ([50a9766](https://github.com/wforney/helia/commit/50a9766297d9a55678c4ab785960b9fa9768715b))
* bump kubo from 0.38.2 to 0.39.0 in the kubo-deps group ([#911](https://github.com/wforney/helia/issues/911)) ([5e06685](https://github.com/wforney/helia/commit/5e0668547b3029ce6ab9fd70081bce70aea950fb))
* bump kubo from 0.39.0 to 0.40.0 ([#963](https://github.com/wforney/helia/issues/963)) ([2d30414](https://github.com/wforney/helia/commit/2d30414a0752c64428a68ef3e15695eb8506b163))
* bump multiformats from 11.0.2 to 12.0.1 ([#4](https://github.com/wforney/helia/issues/4)) ([50bed0f](https://github.com/wforney/helia/commit/50bed0f32b3c07111de804b0e6471e36d8e66626))
* bump multiformats from 11.0.2 to 12.0.1 ([#8](https://github.com/wforney/helia/issues/8)) ([c2a2ee3](https://github.com/wforney/helia/commit/c2a2ee38cc8fa76c8a6d0c92c44023c148148a7e))
* bump multiformats from 11.0.2 to 12.0.1 ([#8](https://github.com/wforney/helia/issues/8)) ([c89b8f1](https://github.com/wforney/helia/commit/c89b8f12d700f0e23dc574cc32f7726d9c9558de))
* bump multiformats from 12.1.3 to 13.0.0 ([#354](https://github.com/wforney/helia/issues/354)) ([1d16bf8](https://github.com/wforney/helia/commit/1d16bf89acd10ac79baf53f0cbc5f92d0e9d8301))
* bump the kubo-deps group across 7 directories with 1 update ([#734](https://github.com/wforney/helia/issues/734)) ([f7155d8](https://github.com/wforney/helia/commit/f7155d8bece43dd91d19060881294f61df9d222c))
* bump the kubo-deps group with 2 updates ([#867](https://github.com/wforney/helia/issues/867)) ([c442439](https://github.com/wforney/helia/commit/c4424392b6d00bf7b144a15f1125990b7388b2b7))
* **dev:** bump @libp2p/websockets from 6.0.3 to 7.0.5 ([#35](https://github.com/wforney/helia/issues/35)) ([de04834](https://github.com/wforney/helia/commit/de048348666a7961cda517ce26f8aedfa987a3bc))
* **dev:** bump @libp2p/websockets from 6.0.3 to 7.0.5 ([#36](https://github.com/wforney/helia/issues/36)) ([5f4169e](https://github.com/wforney/helia/commit/5f4169e9ddb16a7d026db395ad3e9c1a2f764bb7))
* **dev:** bump @multiformats/sha3 from 2.0.17 to 3.0.0 ([#249](https://github.com/wforney/helia/issues/249)) ([7f2dcf8](https://github.com/wforney/helia/commit/7f2dcf8b878f80e75b3d0dc5a3c49caeb0430785))
* **dev:** bump aegir from 39.0.13 to 40.0.11 ([#26](https://github.com/wforney/helia/issues/26)) ([37b6ba1](https://github.com/wforney/helia/commit/37b6ba14e085073b966fced3c3777519601d0a81))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#105](https://github.com/wforney/helia/issues/105)) ([2421ee2](https://github.com/wforney/helia/commit/2421ee2b4440446160e1a665bc5ecfc92d2b64de))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#107](https://github.com/wforney/helia/issues/107)) ([5402d30](https://github.com/wforney/helia/commit/5402d30de1437052e9e9b955d9be3c2898515447))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#273](https://github.com/wforney/helia/issues/273)) ([9a9f637](https://github.com/wforney/helia/commit/9a9f63787223eff7eae3b72e59b79b11baa621ea))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#36](https://github.com/wforney/helia/issues/36)) ([ca3f05a](https://github.com/wforney/helia/commit/ca3f05a74316f53b0e44f5edd6e303b6e8463bf2))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#36](https://github.com/wforney/helia/issues/36)) ([9f57d11](https://github.com/wforney/helia/commit/9f57d11e461a3b1fddbc2a92e225d31eee56613c))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#36](https://github.com/wforney/helia/issues/36)) ([77e29bc](https://github.com/wforney/helia/commit/77e29bcdda33387b8bf15124bc316ef03b434433))
* **dev:** bump aegir from 40.0.13 to 41.0.0 ([#41](https://github.com/wforney/helia/issues/41)) ([e8fc99f](https://github.com/wforney/helia/commit/e8fc99f4e372eaf72c2598f5a7a9942143c6d788))
* **dev:** bump go-ipfs from 0.20.0 to 0.22.0 ([#22](https://github.com/wforney/helia/issues/22)) ([c8a2e7f](https://github.com/wforney/helia/commit/c8a2e7ff11df35b6c7e4e3d336890e5d9f5f51fb))
* **dev:** bump go-ipfs from 0.20.0 to 0.22.0 ([#24](https://github.com/wforney/helia/issues/24)) ([cff694f](https://github.com/wforney/helia/commit/cff694f6bc88b25e71d3243b045c65932bfa9874))
* **dev:** bump go-ipfs from 0.20.0 to 0.22.0 ([#81](https://github.com/wforney/helia/issues/81)) ([15fb863](https://github.com/wforney/helia/commit/15fb86380bff97b54120009fb20a0dc5bfa4cc92))
* **dev:** bump helia from 2.0.1 to 2.0.3 ([#10](https://github.com/wforney/helia/issues/10)) ([6911470](https://github.com/wforney/helia/commit/6911470cb43720798fca571669a166eb3689dad2))
* **dev:** bump kubo from 0.22.0 to 0.23.0 ([#278](https://github.com/wforney/helia/issues/278)) ([51316ba](https://github.com/wforney/helia/commit/51316baa71ec22b91013a7f98b46f5ad420b984a))
* **dev:** bump kubo from 0.24.0 to 0.25.0 ([#351](https://github.com/wforney/helia/issues/351)) ([9efe50d](https://github.com/wforney/helia/commit/9efe50df7f130c062f42b0a391bdb1f1e7e50af8))
* **dev:** bump libp2p from 0.45.9 to 0.46.6 ([#92](https://github.com/wforney/helia/issues/92)) ([efe02e5](https://github.com/wforney/helia/commit/efe02e5b38992189edb40cd34d79e76dca4c34a3))
* go-ipfs -&gt; kubo ([#53](https://github.com/wforney/helia/issues/53)) ([f13daae](https://github.com/wforney/helia/commit/f13daae3d62579b0b181bc5387c5d7b8e10029a5))
* update aegir to 47.x.x ([#804](https://github.com/wforney/helia/issues/804)) ([60fbbc2](https://github.com/wforney/helia/commit/60fbbc2eb08e023e2eac02ae0e89ed143d715084))
* update all deps ([#792](https://github.com/wforney/helia/issues/792)) ([d43efc7](https://github.com/wforney/helia/commit/d43efc7bdfff34071a8e4e22e01f659fbac0b78e))
* update delegated routing client ([#937](https://github.com/wforney/helia/issues/937)) ([1c79dae](https://github.com/wforney/helia/commit/1c79dae55273a2751eb6d11648702f2946df4bcc))
* update ipns to v7.x.x ([#106](https://github.com/wforney/helia/issues/106)) ([83a1d14](https://github.com/wforney/helia/commit/83a1d147e8ba758efd7d2574ea486218bd1f3df2))
* update kad-dht to 14.0.0 ([#648](https://github.com/wforney/helia/issues/648)) ([60d8c8a](https://github.com/wforney/helia/commit/60d8c8a9ff2104302d1c87bcf39258f1da33cd45))
* update libp2p patch versions ([917a1bc](https://github.com/wforney/helia/commit/917a1bceb9e9b56428a15dc3377a963f06affd12))
* updates to libp2p v1 ([#320](https://github.com/wforney/helia/issues/320)) ([635d7a2](https://github.com/wforney/helia/commit/635d7a2938111ccc53f8defbd9b8f8f8ea3e8e6a))


### Refactors

* use functions for block broker creation ([#286](https://github.com/wforney/helia/issues/286)) ([43932a5](https://github.com/wforney/helia/commit/43932a54036dafdf1265b034b30b12784fd22d82))


### Refactors

* use functions for block broker creation ([#286](https://github.com/wforney/helia/issues/286)) ([43932a5](https://github.com/wforney/helia/commit/43932a54036dafdf1265b034b30b12784fd22d82))

## [10.1.3](https://github.com/ipfs/helia/compare/interop-v10.1.2...interop-v10.1.3) (2026-03-06)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.1.2 to ^5.1.3
    * @helia/http bumped from ^3.0.20 to ^3.0.21
    * helia bumped from ^6.0.20 to ^6.0.21

## [10.1.2](https://github.com/ipfs/helia/compare/interop-v10.1.1...interop-v10.1.2) (2026-02-05)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.1.1 to ^5.1.2
    * @helia/car bumped from ^5.3.8 to ^5.3.9
    * @helia/dag-cbor bumped from ^5.0.6 to ^5.0.7
    * @helia/dag-json bumped from ^5.0.6 to ^5.0.7
    * @helia/http bumped from ^3.0.19 to ^3.0.20
    * @helia/interface bumped from ^6.1.0 to ^6.1.1
    * @helia/ipns bumped from ^9.1.8 to ^9.1.9
    * @helia/json bumped from ^5.0.6 to ^5.0.7
    * @helia/mfs bumped from ^7.0.3 to ^7.0.4
    * @helia/routers bumped from ^5.0.2 to ^5.0.3
    * @helia/strings bumped from ^5.0.6 to ^5.0.7
    * @helia/unixfs bumped from ^7.0.3 to ^7.0.4
    * helia bumped from ^6.0.19 to ^6.0.20

## [10.1.1](https://github.com/ipfs/helia/compare/interop-v10.1.0...interop-v10.1.1) (2026-02-05)


### Bug Fixes

* emit provider event for initial providers ([#953](https://github.com/ipfs/helia/issues/953)) ([f058fba](https://github.com/ipfs/helia/commit/f058fba8a06f8afdd3558bdf7c3801381648ffec))
* emit provider event for initial provides ([f058fba](https://github.com/ipfs/helia/commit/f058fba8a06f8afdd3558bdf7c3801381648ffec))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.1.0 to ^5.1.1
    * @helia/car bumped from ^5.3.7 to ^5.3.8
    * @helia/http bumped from ^3.0.18 to ^3.0.19
    * helia bumped from ^6.0.18 to ^6.0.19

## [10.1.0](https://github.com/ipfs/helia/compare/interop-v10.0.1...interop-v10.1.0) (2026-02-04)


### Features

* allow adding peers to session ([#950](https://github.com/ipfs/helia/issues/950)) ([33e4681](https://github.com/ipfs/helia/commit/33e4681394539d4298a028d2d9ff48a14f76a8e3))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.15 to ^5.1.0
    * @helia/car bumped from ^5.3.6 to ^5.3.7
    * @helia/dag-cbor bumped from ^5.0.5 to ^5.0.6
    * @helia/dag-json bumped from ^5.0.5 to ^5.0.6
    * @helia/http bumped from ^3.0.17 to ^3.0.18
    * @helia/interface bumped from ^6.0.3 to ^6.1.0
    * @helia/ipns bumped from ^9.1.7 to ^9.1.8
    * @helia/json bumped from ^5.0.5 to ^5.0.6
    * @helia/mfs bumped from ^7.0.2 to ^7.0.3
    * @helia/routers bumped from ^5.0.1 to ^5.0.2
    * @helia/strings bumped from ^5.0.5 to ^5.0.6
    * @helia/unixfs bumped from ^7.0.2 to ^7.0.3
    * helia bumped from ^6.0.17 to ^6.0.18

## [10.0.1](https://github.com/ipfs/helia/compare/interop-v10.0.0...interop-v10.0.1) (2026-02-02)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.14 to ^5.0.15
    * @helia/car bumped from ^5.3.5 to ^5.3.6
    * @helia/dag-cbor bumped from ^5.0.4 to ^5.0.5
    * @helia/dag-json bumped from ^5.0.4 to ^5.0.5
    * @helia/http bumped from ^3.0.16 to ^3.0.17
    * @helia/interface bumped from ^6.0.2 to ^6.0.3
    * @helia/ipns bumped from ^9.1.6 to ^9.1.7
    * @helia/json bumped from ^5.0.4 to ^5.0.5
    * @helia/mfs bumped from ^7.0.1 to ^7.0.2
    * @helia/routers bumped from ^5.0.0 to ^5.0.1
    * @helia/strings bumped from ^5.0.4 to ^5.0.5
    * @helia/unixfs bumped from ^7.0.1 to ^7.0.2
    * helia bumped from ^6.0.16 to ^6.0.17

## [10.0.0](https://github.com/ipfs/helia/compare/interop-v9.0.18...interop-v10.0.0) (2026-01-16)


### ⚠ BREAKING CHANGES

* pass the endpoint URL to the delegated routing router  as a `url` property of an init object

### Dependencies

* update delegated routing client ([#937](https://github.com/ipfs/helia/issues/937)) ([1c79dae](https://github.com/ipfs/helia/commit/1c79dae55273a2751eb6d11648702f2946df4bcc))
* The following workspace dependencies were updated
  * dependencies
    * @helia/http bumped from ^3.0.15 to ^3.0.16
    * @helia/routers bumped from ^4.0.6 to ^5.0.0
    * helia bumped from ^6.0.15 to ^6.0.16

## [9.0.18](https://github.com/ipfs/helia/compare/interop-v9.0.17...interop-v9.0.18) (2026-01-15)


### Bug Fixes

* use non-deprecated factory function to create delegated client ([#934](https://github.com/ipfs/helia/issues/934)) ([20ba9cf](https://github.com/ipfs/helia/commit/20ba9cf6256961d2b664af0e8f48b5e9d009d834))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.13 to ^5.0.14
    * @helia/dnslink bumped from ^1.1.3 to ^1.1.4
    * @helia/car bumped from ^5.3.4 to ^5.3.5
    * @helia/dag-cbor bumped from ^5.0.3 to ^5.0.4
    * @helia/dag-json bumped from ^5.0.3 to ^5.0.4
    * @helia/http bumped from ^3.0.14 to ^3.0.15
    * @helia/ipns bumped from ^9.1.5 to ^9.1.6
    * @helia/json bumped from ^5.0.3 to ^5.0.4
    * @helia/mfs bumped from ^7.0.0 to ^7.0.1
    * @helia/routers bumped from ^4.0.5 to ^4.0.6
    * @helia/strings bumped from ^5.0.3 to ^5.0.4
    * @helia/unixfs bumped from ^7.0.0 to ^7.0.1
    * helia bumped from ^6.0.14 to ^6.0.15

## [9.0.17](https://github.com/ipfs/helia/compare/interop-v9.0.16...interop-v9.0.17) (2026-01-12)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/car bumped from ^5.3.3 to ^5.3.4
    * @helia/mfs bumped from ^6.0.4 to ^7.0.0
    * @helia/unixfs bumped from ^6.0.4 to ^7.0.0

## [9.0.16](https://github.com/ipfs/helia/compare/interop-v9.0.15...interop-v9.0.16) (2025-12-15)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.12 to ^5.0.13
    * @helia/car bumped from ^5.3.2 to ^5.3.3
    * @helia/http bumped from ^3.0.13 to ^3.0.14
    * helia bumped from ^6.0.13 to ^6.0.14

## [9.0.15](https://github.com/ipfs/helia/compare/interop-v9.0.14...interop-v9.0.15) (2025-12-12)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/ipns bumped from ^9.1.4 to ^9.1.5

## [9.0.14](https://github.com/ipfs/helia/compare/interop-v9.0.13...interop-v9.0.14) (2025-12-12)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.11 to ^5.0.12
    * @helia/car bumped from ^5.3.1 to ^5.3.2
    * @helia/http bumped from ^3.0.12 to ^3.0.13
    * @helia/mfs bumped from ^6.0.3 to ^6.0.4
    * @helia/unixfs bumped from ^6.0.3 to ^6.0.4
    * helia bumped from ^6.0.12 to ^6.0.13

## [9.0.13](https://github.com/ipfs/helia/compare/interop-v9.0.12...interop-v9.0.13) (2025-12-12)


### Dependencies

* bump kubo from 0.38.2 to 0.39.0 in the kubo-deps group ([#911](https://github.com/ipfs/helia/issues/911)) ([5e06685](https://github.com/ipfs/helia/commit/5e0668547b3029ce6ab9fd70081bce70aea950fb))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.10 to ^5.0.11
    * @helia/car bumped from ^5.3.0 to ^5.3.1
    * @helia/http bumped from ^3.0.11 to ^3.0.12
    * @helia/ipns bumped from ^9.1.3 to ^9.1.4
    * @helia/routers bumped from ^4.0.4 to ^4.0.5
    * helia bumped from ^6.0.11 to ^6.0.12

## [9.0.12](https://github.com/ipfs/helia/compare/interop-v9.0.11...interop-v9.0.12) (2025-11-20)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.9 to ^5.0.10
    * @helia/car bumped from ^5.2.5 to ^5.3.0
    * @helia/http bumped from ^3.0.10 to ^3.0.11
    * helia bumped from ^6.0.10 to ^6.0.11

## [9.0.11](https://github.com/ipfs/helia/compare/interop-v9.0.10...interop-v9.0.11) (2025-11-14)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.8 to ^5.0.9
    * @helia/car bumped from ^5.2.4 to ^5.2.5
    * @helia/http bumped from ^3.0.9 to ^3.0.10
    * helia bumped from ^6.0.9 to ^6.0.10

## [9.0.10](https://github.com/ipfs/helia/compare/interop-v9.0.9...interop-v9.0.10) (2025-11-13)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.7 to ^5.0.8
    * @helia/car bumped from ^5.2.3 to ^5.2.4
    * @helia/http bumped from ^3.0.8 to ^3.0.9
    * @helia/routers bumped from ^4.0.3 to ^4.0.4
    * helia bumped from ^6.0.8 to ^6.0.9

## [9.0.9](https://github.com/ipfs/helia/compare/interop-v9.0.8...interop-v9.0.9) (2025-11-10)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/dnslink bumped from ^1.1.2 to ^1.1.3

## [9.0.8](https://github.com/ipfs/helia/compare/interop-v9.0.7...interop-v9.0.8) (2025-10-29)


### Bug Fixes

* use libp2p provider routing field ([#889](https://github.com/ipfs/helia/issues/889)) ([d4d97b8](https://github.com/ipfs/helia/commit/d4d97b83f76be7e3b480052467408839f808e230))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.6 to ^5.0.7
    * @helia/dnslink bumped from ^1.1.1 to ^1.1.2
    * @helia/car bumped from ^5.2.2 to ^5.2.3
    * @helia/dag-cbor bumped from ^5.0.2 to ^5.0.3
    * @helia/dag-json bumped from ^5.0.2 to ^5.0.3
    * @helia/http bumped from ^3.0.7 to ^3.0.8
    * @helia/interface bumped from ^6.0.1 to ^6.0.2
    * @helia/ipns bumped from ^9.1.2 to ^9.1.3
    * @helia/json bumped from ^5.0.2 to ^5.0.3
    * @helia/mfs bumped from ^6.0.2 to ^6.0.3
    * @helia/routers bumped from ^4.0.2 to ^4.0.3
    * @helia/strings bumped from ^5.0.2 to ^5.0.3
    * @helia/unixfs bumped from ^6.0.2 to ^6.0.3
    * helia bumped from ^6.0.7 to ^6.0.8

## [9.0.7](https://github.com/ipfs/helia/compare/interop-v9.0.6...interop-v9.0.7) (2025-10-27)


### Bug Fixes

* add provider events to bitswap and trustless gateways ([#888](https://github.com/ipfs/helia/issues/888)) ([95d95da](https://github.com/ipfs/helia/commit/95d95dad7ff2a1e462b5a8a4f57ac40c4503f4ef))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.5 to ^5.0.6
    * @helia/car bumped from ^5.2.1 to ^5.2.2
    * @helia/dag-cbor bumped from ^5.0.1 to ^5.0.2
    * @helia/dag-json bumped from ^5.0.1 to ^5.0.2
    * @helia/http bumped from ^3.0.6 to ^3.0.7
    * @helia/interface bumped from ^6.0.0 to ^6.0.1
    * @helia/ipns bumped from ^9.1.1 to ^9.1.2
    * @helia/json bumped from ^5.0.1 to ^5.0.2
    * @helia/mfs bumped from ^6.0.1 to ^6.0.2
    * @helia/routers bumped from ^4.0.1 to ^4.0.2
    * @helia/strings bumped from ^5.0.1 to ^5.0.2
    * @helia/unixfs bumped from ^6.0.1 to ^6.0.2
    * helia bumped from ^6.0.6 to ^6.0.7

## [9.0.6](https://github.com/ipfs/helia/compare/interop-v9.0.5...interop-v9.0.6) (2025-10-22)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.4 to ^5.0.5
    * @helia/dnslink bumped from ^1.1.0 to ^1.1.1
    * @helia/car bumped from ^5.2.0 to ^5.2.1
    * @helia/http bumped from ^3.0.5 to ^3.0.6
    * @helia/ipns bumped from ^9.1.0 to ^9.1.1
    * helia bumped from ^6.0.5 to ^6.0.6

## [9.0.5](https://github.com/ipfs/helia/compare/interop-v9.0.4...interop-v9.0.5) (2025-10-20)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.3 to ^5.0.4
    * @helia/car bumped from ^5.1.1 to ^5.2.0
    * @helia/http bumped from ^3.0.4 to ^3.0.5
    * helia bumped from ^6.0.4 to ^6.0.5

## [9.0.4](https://github.com/ipfs/helia/compare/interop-v9.0.3...interop-v9.0.4) (2025-10-17)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.2 to ^5.0.3
    * @helia/car bumped from ^5.1.0 to ^5.1.1
    * @helia/http bumped from ^3.0.3 to ^3.0.4
    * helia bumped from ^6.0.3 to ^6.0.4

## [9.0.3](https://github.com/ipfs/helia/compare/interop-v9.0.2...interop-v9.0.3) (2025-10-17)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.1 to ^5.0.2
    * @helia/car bumped from ^5.0.1 to ^5.1.0
    * @helia/http bumped from ^3.0.2 to ^3.0.3
    * helia bumped from ^6.0.2 to ^6.0.3

## [9.0.2](https://github.com/ipfs/helia/compare/interop-v9.0.1...interop-v9.0.2) (2025-10-14)


### Dependencies

* bump the kubo-deps group with 2 updates ([#867](https://github.com/ipfs/helia/issues/867)) ([c442439](https://github.com/ipfs/helia/commit/c4424392b6d00bf7b144a15f1125990b7388b2b7))
* The following workspace dependencies were updated
  * dependencies
    * @helia/dnslink bumped from ^1.0.1 to ^1.1.0
    * @helia/http bumped from ^3.0.1 to ^3.0.2
    * @helia/ipns bumped from ^9.0.0 to ^9.1.0
    * @helia/routers bumped from ^4.0.0 to ^4.0.1
    * helia bumped from ^6.0.1 to ^6.0.2

## [9.0.1](https://github.com/ipfs/helia/compare/interop-v9.0.0...interop-v9.0.1) (2025-10-09)


### Bug Fixes

* enforce maximum identity hash size ([#865](https://github.com/ipfs/helia/issues/865)) ([d9051cd](https://github.com/ipfs/helia/commit/d9051cdc2fd19ab7def32d195b5798b27d85a078)), closes [#846](https://github.com/ipfs/helia/issues/846)
* support multiple DNSLink entries ([#863](https://github.com/ipfs/helia/issues/863)) ([fe38409](https://github.com/ipfs/helia/commit/fe384098a0930915eff4c41d562606955e0e710d)), closes [#368](https://github.com/ipfs/helia/issues/368)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^5.0.0 to ^5.0.1
    * @helia/dnslink bumped from ^1.0.0 to ^1.0.1
    * @helia/car bumped from ^5.0.0 to ^5.0.1
    * @helia/dag-cbor bumped from ^5.0.0 to ^5.0.1
    * @helia/dag-json bumped from ^5.0.0 to ^5.0.1
    * @helia/http bumped from ^3.0.0 to ^3.0.1
    * @helia/json bumped from ^5.0.0 to ^5.0.1
    * @helia/mfs bumped from ^6.0.0 to ^6.0.1
    * @helia/strings bumped from ^5.0.0 to ^5.0.1
    * @helia/unixfs bumped from ^6.0.0 to ^6.0.1
    * helia bumped from ^6.0.0 to ^6.0.1

## [9.0.0](https://github.com/ipfs/helia/compare/interop-v8.3.0...interop-v9.0.0) (2025-10-09)


### ⚠ BREAKING CHANGES

* `ipns.publish` now accepts key name strings rather than private keys Names previously publishing using an user controlled private key, will need to be explicitly published again by first importing the key into the keychain (`await libp2p.keychain.importKey('my-key', key)` and then published with `ipns.publish('my-key', ...)`.
* car.stream has been renamed car.export
* uses libp2p v3 and updated block/data stores

### Features

* add ipns reproviding/republishing ([#764](https://github.com/ipfs/helia/issues/764)) ([008747b](https://github.com/ipfs/helia/commit/008747b59a03682e1b6f648a39635e1b1971e481))
* rename car stream to export ([#859](https://github.com/ipfs/helia/issues/859)) ([63338b9](https://github.com/ipfs/helia/commit/63338b9c261a1120592e5afb256dfa8c8feed16b))
* update to libp2p@v3 and latest data/block stores ([#856](https://github.com/ipfs/helia/issues/856)) ([34d3ecd](https://github.com/ipfs/helia/commit/34d3ecd76c8424387c57221000e226f08ccd1d1e))


### Bug Fixes

* @helia/* modules validate CID codec ([#643](https://github.com/ipfs/helia/issues/643)) ([93aa464](https://github.com/ipfs/helia/commit/93aa46459dcff81f0e5eef479f76e39ef5f03736))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.2.4 to ^5.0.0
    * @helia/dnslink bumped from ^0.0.0 to ^1.0.0
    * @helia/car bumped from ^4.2.0 to ^5.0.0
    * @helia/dag-cbor bumped from ^4.1.0 to ^5.0.0
    * @helia/dag-json bumped from ^4.1.0 to ^5.0.0
    * @helia/http bumped from ^2.2.1 to ^3.0.0
    * @helia/interface bumped from ^5.4.0 to ^6.0.0
    * @helia/ipns bumped from ^8.2.4 to ^9.0.0
    * @helia/json bumped from ^4.0.7 to ^5.0.0
    * @helia/mfs bumped from ^5.1.0 to ^6.0.0
    * @helia/routers bumped from ^3.1.3 to ^4.0.0
    * @helia/strings bumped from ^4.1.0 to ^5.0.0
    * @helia/unixfs bumped from ^5.1.0 to ^6.0.0
    * helia bumped from ^5.5.1 to ^6.0.0

## [8.3.0](https://github.com/ipfs/helia/compare/interop-v8.2.0...interop-v8.3.0) (2025-07-31)


### Features

* expose providers option ([#834](https://github.com/ipfs/helia/issues/834)) ([5a911c6](https://github.com/ipfs/helia/commit/5a911c6977ec47d1906ccc69b5f57667f22d9ccf))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.2.3 to ^4.2.4
    * @helia/car bumped from ^4.1.3 to ^4.2.0
    * @helia/dag-cbor bumped from ^4.0.7 to ^4.1.0
    * @helia/dag-json bumped from ^4.0.7 to ^4.1.0
    * @helia/http bumped from ^2.2.0 to ^2.2.1
    * @helia/mfs bumped from ^5.0.4 to ^5.1.0
    * @helia/strings bumped from ^4.0.7 to ^4.1.0
    * @helia/unixfs bumped from ^5.0.4 to ^5.1.0
    * helia bumped from ^5.5.0 to ^5.5.1

## [8.2.0](https://github.com/ipfs/helia/compare/interop-v8.1.2...interop-v8.2.0) (2025-07-22)


### Features

* add libp2p to @helia/http ([#826](https://github.com/ipfs/helia/issues/826)) ([235e5c4](https://github.com/ipfs/helia/commit/235e5c4093a51bda1e0331f9dd26754f601b582c))


### Dependencies

* bump kubo from 0.34.1 to 0.35.0 in the kubo-deps group ([#806](https://github.com/ipfs/helia/issues/806)) ([50a9766](https://github.com/ipfs/helia/commit/50a9766297d9a55678c4ab785960b9fa9768715b))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.2.2 to ^4.2.3
    * @helia/car bumped from ^4.1.2 to ^4.1.3
    * @helia/dag-cbor bumped from ^4.0.6 to ^4.0.7
    * @helia/dag-json bumped from ^4.0.6 to ^4.0.7
    * @helia/http bumped from ^2.1.2 to ^2.2.0
    * @helia/interface bumped from ^5.3.2 to ^5.4.0
    * @helia/ipns bumped from ^8.2.3 to ^8.2.4
    * @helia/json bumped from ^4.0.6 to ^4.0.7
    * @helia/mfs bumped from ^5.0.3 to ^5.0.4
    * @helia/routers bumped from ^3.1.2 to ^3.1.3
    * @helia/strings bumped from ^4.0.6 to ^4.0.7
    * @helia/unixfs bumped from ^5.0.3 to ^5.0.4
    * helia bumped from ^5.4.2 to ^5.5.0

## [8.1.2](https://github.com/ipfs/helia/compare/interop-v8.1.1...interop-v8.1.2) (2025-05-20)


### Dependencies

* update aegir to 47.x.x ([#804](https://github.com/ipfs/helia/issues/804)) ([60fbbc2](https://github.com/ipfs/helia/commit/60fbbc2eb08e023e2eac02ae0e89ed143d715084))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.2.1 to ^4.2.2
    * @helia/car bumped from ^4.1.1 to ^4.1.2
    * @helia/dag-cbor bumped from ^4.0.5 to ^4.0.6
    * @helia/dag-json bumped from ^4.0.5 to ^4.0.6
    * @helia/http bumped from ^2.1.1 to ^2.1.2
    * @helia/interface bumped from ^5.3.1 to ^5.3.2
    * @helia/ipns bumped from ^8.2.2 to ^8.2.3
    * @helia/json bumped from ^4.0.5 to ^4.0.6
    * @helia/mfs bumped from ^5.0.2 to ^5.0.3
    * @helia/routers bumped from ^3.1.1 to ^3.1.2
    * @helia/strings bumped from ^4.0.5 to ^4.0.6
    * @helia/unixfs bumped from ^5.0.2 to ^5.0.3
    * helia bumped from ^5.4.1 to ^5.4.2

## [8.1.1](https://github.com/ipfs/helia/compare/interop-v8.1.0...interop-v8.1.1) (2025-05-13)


### Dependencies

* update all deps ([#792](https://github.com/ipfs/helia/issues/792)) ([d43efc7](https://github.com/ipfs/helia/commit/d43efc7bdfff34071a8e4e22e01f659fbac0b78e))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.2.0 to ^4.2.1
    * @helia/car bumped from ^4.1.0 to ^4.1.1
    * @helia/dag-cbor bumped from ^4.0.4 to ^4.0.5
    * @helia/dag-json bumped from ^4.0.4 to ^4.0.5
    * @helia/http bumped from ^2.1.0 to ^2.1.1
    * @helia/interface bumped from ^5.3.0 to ^5.3.1
    * @helia/ipns bumped from ^8.2.1 to ^8.2.2
    * @helia/json bumped from ^4.0.4 to ^4.0.5
    * @helia/mfs bumped from ^5.0.1 to ^5.0.2
    * @helia/routers bumped from ^3.1.0 to ^3.1.1
    * @helia/strings bumped from ^4.0.4 to ^4.0.5
    * @helia/unixfs bumped from ^5.0.1 to ^5.0.2
    * helia bumped from ^5.4.0 to ^5.4.1

## [8.1.0](https://github.com/ipfs/helia/compare/interop-v8.0.0...interop-v8.1.0) (2025-05-13)


### Features

* pass initial providers to session ([#777](https://github.com/ipfs/helia/issues/777)) ([3d77369](https://github.com/ipfs/helia/commit/3d773698389deb70e1a0181eb81fb8b5992857b8))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.1.0 to ^4.2.0
    * @helia/car bumped from ^4.0.4 to ^4.1.0
    * @helia/dag-cbor bumped from ^4.0.3 to ^4.0.4
    * @helia/dag-json bumped from ^4.0.3 to ^4.0.4
    * @helia/http bumped from ^2.0.5 to ^2.1.0
    * @helia/interface bumped from ^5.2.1 to ^5.3.0
    * @helia/ipns bumped from ^8.2.0 to ^8.2.1
    * @helia/json bumped from ^4.0.3 to ^4.0.4
    * @helia/mfs bumped from ^5.0.0 to ^5.0.1
    * @helia/routers bumped from ^3.0.1 to ^3.1.0
    * @helia/strings bumped from ^4.0.3 to ^4.0.4
    * @helia/unixfs bumped from ^5.0.0 to ^5.0.1
    * helia bumped from ^5.3.0 to ^5.4.0

## [8.0.0](https://github.com/ipfs/helia/compare/interop-v7.1.3...interop-v8.0.0) (2025-03-20)


### ⚠ BREAKING CHANGES

* Fields that would involve DAG traversal have been removed from the output of `fs.stat` - pass the `extended` option to have them returned

### Bug Fixes

* return simple stats or extended stats ([#760](https://github.com/ipfs/helia/issues/760)) ([325b36f](https://github.com/ipfs/helia/commit/325b36f70624d3dcc25b2723f9e3e2d26e1e5199))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/car bumped from ^4.0.3 to ^4.0.4
    * @helia/mfs bumped from ^4.0.3 to ^5.0.0
    * @helia/unixfs bumped from ^4.0.3 to ^5.0.0

## [7.1.3](https://github.com/ipfs/helia/compare/interop-v7.1.2...interop-v7.1.3) (2025-03-13)


### Bug Fixes

* use bytestream methods to add byte streams ([#758](https://github.com/ipfs/helia/issues/758)) ([70b8fa9](https://github.com/ipfs/helia/commit/70b8fa96cb5fe0fddbb0e1528e6685778af90aa8))


### Documentation

* add spell checker to ci ([#743](https://github.com/ipfs/helia/issues/743)) ([45ca6bc](https://github.com/ipfs/helia/commit/45ca6bc70b1644028500101044595fa0e2199b07))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.0.4 to ^4.1.0
    * @helia/car bumped from ^4.0.2 to ^4.0.3
    * @helia/dag-cbor bumped from ^4.0.2 to ^4.0.3
    * @helia/dag-json bumped from ^4.0.2 to ^4.0.3
    * @helia/http bumped from ^2.0.4 to ^2.0.5
    * @helia/interface bumped from ^5.2.0 to ^5.2.1
    * @helia/ipns bumped from ^8.1.0 to ^8.2.0
    * @helia/json bumped from ^4.0.2 to ^4.0.3
    * @helia/mfs bumped from ^4.0.2 to ^4.0.3
    * @helia/routers bumped from ^3.0.0 to ^3.0.1
    * @helia/strings bumped from ^4.0.2 to ^4.0.3
    * @helia/unixfs bumped from ^4.0.2 to ^4.0.3
    * helia bumped from ^5.2.1 to ^5.3.0

## [7.1.2](https://github.com/ipfs/helia/compare/interop-v7.1.1...interop-v7.1.2) (2025-02-10)


### Dependencies

* bump the kubo-deps group across 7 directories with 1 update ([#734](https://github.com/ipfs/helia/issues/734)) ([f7155d8](https://github.com/ipfs/helia/commit/f7155d8bece43dd91d19060881294f61df9d222c))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.0.3 to ^4.0.4
    * @helia/http bumped from ^2.0.3 to ^2.0.4
    * helia bumped from ^5.2.0 to ^5.2.1

## [7.1.1](https://github.com/ipfs/helia/compare/interop-v7.1.0...interop-v7.1.1) (2025-01-24)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/ipns bumped from ^8.0.2 to ^8.1.0

## [7.1.0](https://github.com/ipfs/helia/compare/interop-v7.0.3...interop-v7.1.0) (2025-01-14)


### Features

* add auto-tls support ([#716](https://github.com/ipfs/helia/issues/716)) ([e45e1de](https://github.com/ipfs/helia/commit/e45e1dea40120b993f009f8fbb81a9737742196c))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.0.2 to ^4.0.3
    * @helia/car bumped from ^4.0.1 to ^4.0.2
    * @helia/dag-cbor bumped from ^4.0.1 to ^4.0.2
    * @helia/dag-json bumped from ^4.0.1 to ^4.0.2
    * @helia/http bumped from ^2.0.2 to ^2.0.3
    * @helia/interface bumped from ^5.1.0 to ^5.2.0
    * @helia/ipns bumped from ^8.0.1 to ^8.0.2
    * @helia/json bumped from ^4.0.1 to ^4.0.2
    * @helia/mfs bumped from ^4.0.1 to ^4.0.2
    * @helia/routers bumped from ^2.2.0 to ^3.0.0
    * @helia/strings bumped from ^4.0.1 to ^4.0.2
    * @helia/unixfs bumped from ^4.0.1 to ^4.0.2
    * helia bumped from ^5.1.1 to ^5.2.0

## [7.0.3](https://github.com/ipfs/helia/compare/interop-v7.0.2...interop-v7.0.3) (2024-11-18)


### Dependencies

* bump aegir from 44.1.4 to 45.0.1 ([#669](https://github.com/ipfs/helia/issues/669)) ([e58e49c](https://github.com/ipfs/helia/commit/e58e49c6aed8ea9d1e9851435a25e33fdbee3781))
* bump kubo from 0.31.0 to 0.32.0 ([#679](https://github.com/ipfs/helia/issues/679)) ([c09fef2](https://github.com/ipfs/helia/commit/c09fef29b749eecf969f9812dea7ab49477582f7))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.0.1 to ^4.0.2
    * @helia/car bumped from ^4.0.0 to ^4.0.1
    * @helia/dag-cbor bumped from ^4.0.0 to ^4.0.1
    * @helia/dag-json bumped from ^4.0.0 to ^4.0.1
    * @helia/http bumped from ^2.0.1 to ^2.0.2
    * @helia/interface bumped from ^5.0.0 to ^5.1.0
    * @helia/ipns bumped from ^8.0.0 to ^8.0.1
    * @helia/json bumped from ^4.0.0 to ^4.0.1
    * @helia/mfs bumped from ^4.0.0 to ^4.0.1
    * @helia/routers bumped from ^2.1.0 to ^2.2.0
    * @helia/strings bumped from ^4.0.0 to ^4.0.1
    * @helia/unixfs bumped from ^4.0.0 to ^4.0.1
    * helia bumped from ^5.1.0 to ^5.1.1

## [7.0.2](https://github.com/ipfs/helia/compare/interop-v7.0.1...interop-v7.0.2) (2024-10-23)


### Dependencies

* bump kubo from 0.30.0 to 0.31.0 ([#656](https://github.com/ipfs/helia/issues/656)) ([8364296](https://github.com/ipfs/helia/commit/83642961c7c6417e58229226048d69a642edcfff))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^4.0.0 to ^4.0.1
    * @helia/http bumped from ^2.0.0 to ^2.0.1
    * @helia/routers bumped from ^2.0.0 to ^2.1.0
    * helia bumped from ^5.0.1 to ^5.1.0

## [7.0.1](https://github.com/ipfs/helia/compare/interop-v7.0.0...interop-v7.0.1) (2024-10-16)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * helia bumped from ^5.0.0 to ^5.0.1

## [7.0.0](https://github.com/ipfs/helia/compare/interop-v6.1.8...interop-v7.0.0) (2024-10-07)


### ⚠ BREAKING CHANGES

* helia now uses libp2p@2.x.x

### Bug Fixes

* add doc-check script and export types used by functions ([#637](https://github.com/ipfs/helia/issues/637)) ([4f14996](https://github.com/ipfs/helia/commit/4f14996a9b976f2b60f4c8fe52a4fd1632420749))
* update to libp2p@2.x.x ([#630](https://github.com/ipfs/helia/issues/630)) ([ec8bf66](https://github.com/ipfs/helia/commit/ec8bf66dd870b42d6e5ef2b41706102397e0d39a))
* use hasCode from multiformats ([#635](https://github.com/ipfs/helia/issues/635)) ([f5a03fc](https://github.com/ipfs/helia/commit/f5a03fc28d0cd59841b842306f912c092aeabd5f))


### Dependencies

* update kad-dht to 14.0.0 ([#648](https://github.com/ipfs/helia/issues/648)) ([60d8c8a](https://github.com/ipfs/helia/commit/60d8c8a9ff2104302d1c87bcf39258f1da33cd45))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^3.0.4 to ^4.0.0
    * @helia/car bumped from ^3.2.1 to ^4.0.0
    * @helia/dag-cbor bumped from ^3.0.6 to ^4.0.0
    * @helia/dag-json bumped from ^3.0.6 to ^4.0.0
    * @helia/http bumped from ^1.0.11 to ^2.0.0
    * @helia/interface bumped from ^4.3.1 to ^5.0.0
    * @helia/ipns bumped from ^7.2.3 to ^8.0.0
    * @helia/json bumped from ^3.0.6 to ^4.0.0
    * @helia/mfs bumped from ^3.0.8 to ^4.0.0
    * @helia/routers bumped from ^1.1.1 to ^2.0.0
    * @helia/strings bumped from ^3.0.6 to ^4.0.0
    * @helia/unixfs bumped from ^3.0.7 to ^4.0.0
    * helia bumped from ^4.2.6 to ^5.0.0

## [6.1.8](https://github.com/ipfs/helia/compare/interop-v6.1.7...interop-v6.1.8) (2024-09-13)


### Bug Fixes

* test for subscribers to ipns pubsub topic ([#584](https://github.com/ipfs/helia/issues/584)) ([c9c644c](https://github.com/ipfs/helia/commit/c9c644c11657ec1411b3f04933fa62501151f732))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^3.0.3 to ^3.0.4
    * @helia/car bumped from ^3.2.0 to ^3.2.1
    * @helia/dag-cbor bumped from ^3.0.5 to ^3.0.6
    * @helia/dag-json bumped from ^3.0.5 to ^3.0.6
    * @helia/http bumped from ^1.0.10 to ^1.0.11
    * @helia/json bumped from ^3.0.5 to ^3.0.6
    * @helia/mfs bumped from ^3.0.7 to ^3.0.8
    * @helia/strings bumped from ^3.0.5 to ^3.0.6
    * helia bumped from ^4.2.5 to ^4.2.6

## [6.1.7](https://github.com/ipfs/helia/compare/interop-v6.1.6...interop-v6.1.7) (2024-07-31)


### Bug Fixes

* update js-libp2p types ([#570](https://github.com/ipfs/helia/issues/570)) ([b4877b5](https://github.com/ipfs/helia/commit/b4877b5b768895684be90a26f4303ae65fc209e7))


### Documentation

* fix grammar - it's -&gt; its ([#565](https://github.com/ipfs/helia/issues/565)) ([155e24d](https://github.com/ipfs/helia/commit/155e24db8c06c33972895d702a656e0c2996f3d9))


### Dependencies

* bump aegir from 42.2.11 to 43.0.1 ([#552](https://github.com/ipfs/helia/issues/552)) ([74ccc92](https://github.com/ipfs/helia/commit/74ccc92793a6d0bb4bee714d9fe4fa4183aa4ee8))
* bump aegir from 43.0.3 to 44.0.1 ([#569](https://github.com/ipfs/helia/issues/569)) ([6952f05](https://github.com/ipfs/helia/commit/6952f05357844e5aa3dffb2afaf261df06b9b7c1))
* bump kubo from 0.28.0 to 0.29.0 ([#555](https://github.com/ipfs/helia/issues/555)) ([117198f](https://github.com/ipfs/helia/commit/117198f85511bfe339b96b588cd62015ed6e69a4))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^3.0.2 to ^3.0.3
    * @helia/car bumped from ^3.1.5 to ^3.2.0
    * @helia/dag-cbor bumped from ^3.0.4 to ^3.0.5
    * @helia/dag-json bumped from ^3.0.4 to ^3.0.5
    * @helia/http bumped from ^1.0.9 to ^1.0.10
    * @helia/interface bumped from ^4.3.0 to ^4.3.1
    * @helia/ipns bumped from ^7.2.2 to ^7.2.3
    * @helia/json bumped from ^3.0.4 to ^3.0.5
    * @helia/mfs bumped from ^3.0.6 to ^3.0.7
    * @helia/routers bumped from ^1.1.0 to ^1.1.1
    * @helia/strings bumped from ^3.0.4 to ^3.0.5
    * @helia/unixfs bumped from ^3.0.6 to ^3.0.7
    * helia bumped from ^4.2.4 to ^4.2.5

## [6.1.6](https://github.com/ipfs/helia/compare/interop-v6.1.5...interop-v6.1.6) (2024-06-18)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * helia bumped from ^4.2.3 to ^4.2.4

## [6.1.5](https://github.com/ipfs/helia/compare/interop-v6.1.4...interop-v6.1.5) (2024-05-27)


### Bug Fixes

* do not depend on external domains in dnslink tests ([#547](https://github.com/ipfs/helia/issues/547)) ([21ef20c](https://github.com/ipfs/helia/commit/21ef20cd05e4d0231d0e3d7d2cfbd21fb75b78a2))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^3.0.1 to ^3.0.2
    * @helia/http bumped from ^1.0.8 to ^1.0.9
    * helia bumped from ^4.2.2 to ^4.2.3

## [6.1.4](https://github.com/ipfs/helia/compare/interop-v6.1.3...interop-v6.1.4) (2024-05-20)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^3.0.0 to ^3.0.1
    * @helia/http bumped from ^1.0.7 to ^1.0.8
    * helia bumped from ^4.2.1 to ^4.2.2

## [6.1.3](https://github.com/ipfs/helia/compare/interop-v6.1.2...interop-v6.1.3) (2024-05-02)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^2.1.2 to ^3.0.0
    * @helia/http bumped from ^1.0.6 to ^1.0.7
    * helia bumped from ^4.2.0 to ^4.2.1

## [6.1.2](https://github.com/ipfs/helia/compare/interop-v6.1.1...interop-v6.1.2) (2024-05-01)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^2.1.1 to ^2.1.2
    * @helia/car bumped from ^3.1.4 to ^3.1.5
    * @helia/dag-cbor bumped from ^3.0.3 to ^3.0.4
    * @helia/dag-json bumped from ^3.0.3 to ^3.0.4
    * @helia/http bumped from ^1.0.5 to ^1.0.6
    * @helia/interface bumped from ^4.2.0 to ^4.3.0
    * @helia/ipns bumped from ^7.2.1 to ^7.2.2
    * @helia/json bumped from ^3.0.3 to ^3.0.4
    * @helia/mfs bumped from ^3.0.5 to ^3.0.6
    * @helia/routers bumped from ^1.0.3 to ^1.1.0
    * @helia/strings bumped from ^3.0.3 to ^3.0.4
    * @helia/unixfs bumped from ^3.0.5 to ^3.0.6
    * helia bumped from ^4.1.2 to ^4.2.0

## [6.1.1](https://github.com/ipfs/helia/compare/interop-v6.1.0...interop-v6.1.1) (2024-04-22)


### Dependencies

* bump ipfsd-ctl from 13.0.0 to 14.0.0 ([#505](https://github.com/ipfs/helia/issues/505)) ([97fb1a7](https://github.com/ipfs/helia/commit/97fb1a78a2e585a66861a2d0fdc4eabf8b28bd04))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^2.1.0 to ^2.1.1
    * @helia/car bumped from ^3.1.3 to ^3.1.4
    * @helia/http bumped from ^1.0.4 to ^1.0.5
    * @helia/mfs bumped from ^3.0.4 to ^3.0.5
    * @helia/unixfs bumped from ^3.0.4 to ^3.0.5
    * helia bumped from ^4.1.1 to ^4.1.2

## [6.1.0](https://github.com/ipfs/helia/compare/interop-v6.0.2...interop-v6.1.0) (2024-04-15)


### Features

* add @helia/bitswap with sessions ([#409](https://github.com/ipfs/helia/issues/409)) ([e582c63](https://github.com/ipfs/helia/commit/e582c63ca296c789312f5fcf5e3e18f267f74c03))


### Bug Fixes

* add sideEffects: false to package.json ([#485](https://github.com/ipfs/helia/issues/485)) ([8c45267](https://github.com/ipfs/helia/commit/8c45267a474ab10b2faadfebdab33cfe446e8c03))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^2.0.3 to ^2.1.0
    * @helia/car bumped from ^3.1.2 to ^3.1.3
    * @helia/dag-cbor bumped from ^3.0.2 to ^3.0.3
    * @helia/dag-json bumped from ^3.0.2 to ^3.0.3
    * @helia/http bumped from ^1.0.3 to ^1.0.4
    * @helia/interface bumped from ^4.1.0 to ^4.2.0
    * @helia/ipns bumped from ^7.2.0 to ^7.2.1
    * @helia/json bumped from ^3.0.2 to ^3.0.3
    * @helia/mfs bumped from ^3.0.3 to ^3.0.4
    * @helia/routers bumped from ^1.0.2 to ^1.0.3
    * @helia/strings bumped from ^3.0.2 to ^3.0.3
    * @helia/unixfs bumped from ^3.0.3 to ^3.0.4
    * helia bumped from ^4.1.0 to ^4.1.1

## [6.0.2](https://github.com/ipfs/helia/compare/interop-v6.0.1...interop-v6.0.2) (2024-04-03)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/car bumped from ^3.1.1 to ^3.1.2
    * @helia/ipns bumped from ^7.1.0 to ^7.2.0
    * @helia/mfs bumped from ^3.0.2 to ^3.0.3
    * @helia/unixfs bumped from ^3.0.2 to ^3.0.3

## [6.0.1](https://github.com/ipfs/helia/compare/interop-v6.0.0...interop-v6.0.1) (2024-03-15)


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/ipns bumped from ^7.0.0 to ^7.1.0

## [6.0.0](https://github.com/ipfs/helia/compare/interop-v5.1.0...interop-v6.0.0) (2024-03-14)


### ⚠ BREAKING CHANGES

* requires @helia/interface@4.1.x or later, `resolveDns` has been renamed `resolveDNSLink`

### Features

* use custom DNS resolver in @helia/ipns for DNSLink ([#466](https://github.com/ipfs/helia/issues/466)) ([2c71b6e](https://github.com/ipfs/helia/commit/2c71b6ec8d34dcc722a3914702f67603492c335f)), closes [#369](https://github.com/ipfs/helia/issues/369)


### Dependencies

* bump kubo from 0.26.0 to 0.27.0 ([#461](https://github.com/ipfs/helia/issues/461)) ([c69913c](https://github.com/ipfs/helia/commit/c69913c546f2bb74344f804f25a93f23adeb9b49))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^2.0.2 to ^2.0.3
    * @helia/car bumped from ^3.1.0 to ^3.1.1
    * @helia/dag-cbor bumped from ^3.0.1 to ^3.0.2
    * @helia/dag-json bumped from ^3.0.1 to ^3.0.2
    * @helia/http bumped from ^1.0.2 to ^1.0.3
    * @helia/interface bumped from ^4.0.1 to ^4.1.0
    * @helia/ipns bumped from ^6.0.1 to ^7.0.0
    * @helia/json bumped from ^3.0.1 to ^3.0.2
    * @helia/mfs bumped from ^3.0.1 to ^3.0.2
    * @helia/routers bumped from ^1.0.1 to ^1.0.2
    * @helia/strings bumped from ^3.0.1 to ^3.0.2
    * @helia/unixfs bumped from ^3.0.1 to ^3.0.2
    * helia bumped from ^4.0.2 to ^4.1.0

## [5.1.0](https://github.com/ipfs/helia/compare/interop-v5.0.0...interop-v5.1.0) (2024-02-28)


### Features

* create @helia/verified-fetch ([#392](https://github.com/ipfs/helia/issues/392)) ([f243de2](https://github.com/ipfs/helia/commit/f243de26eda64951c2909121730b6a1b8a689bf6))
* require content-type parser to set content-type ([#423](https://github.com/ipfs/helia/issues/423)) ([f58d467](https://github.com/ipfs/helia/commit/f58d467108e0b99d1e15b18a899ef81082ad59a7))


### Bug Fixes

* allow contentTypeParser with Helia instance ([#427](https://github.com/ipfs/helia/issues/427)) ([3283a5c](https://github.com/ipfs/helia/commit/3283a5c91ce87894f2b9d7c93126fc74647ba17d))
* update project deps and docs ([77e34fc](https://github.com/ipfs/helia/commit/77e34fc115cbfb82585fd954bcf389ecebf655bc))
* use unixfs exporter to traverse DAGs ([#455](https://github.com/ipfs/helia/issues/455)) ([6f8c15b](https://github.com/ipfs/helia/commit/6f8c15b769c08bf73e7c62dab79909b5ecfc3c93))


### Dependencies

* bump @chainsafe/libp2p-gossipsub from 11.2.1 to 12.0.0 ([#430](https://github.com/ipfs/helia/issues/430)) ([9b1ddf8](https://github.com/ipfs/helia/commit/9b1ddf85e503ecf5c3ddaa04826bef2f75454b44))
* bump @chainsafe/libp2p-gossipsub from 12.0.0 to 13.0.0 ([#457](https://github.com/ipfs/helia/issues/457)) ([cb35a1b](https://github.com/ipfs/helia/commit/cb35a1ba149628181b3bb48e14d927d2ebc9c23b))
* update libp2p patch versions ([917a1bc](https://github.com/ipfs/helia/commit/917a1bceb9e9b56428a15dc3377a963f06affd12))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^2.0.1 to ^2.0.2
    * @helia/car bumped from ^3.0.0 to ^3.1.0
    * @helia/dag-cbor bumped from ^3.0.0 to ^3.0.1
    * @helia/dag-json bumped from ^3.0.0 to ^3.0.1
    * @helia/http bumped from ^1.0.1 to ^1.0.2
    * @helia/interface bumped from ^4.0.0 to ^4.0.1
    * @helia/ipns bumped from ^6.0.0 to ^6.0.1
    * @helia/json bumped from ^3.0.0 to ^3.0.1
    * @helia/mfs bumped from ^3.0.0 to ^3.0.1
    * @helia/routers bumped from ^1.0.0 to ^1.0.1
    * @helia/strings bumped from ^3.0.0 to ^3.0.1
    * @helia/unixfs bumped from ^3.0.0 to ^3.0.1
    * helia bumped from ^4.0.1 to ^4.0.2

## [5.0.0](https://github.com/ipfs/helia/compare/interop-v4.0.0...interop-v5.0.0) (2024-01-31)


### ⚠ BREAKING CHANGES

* to support paths in `@helia/ipns`, the return type of `ipns.resolve` is now `{ path: string, cid: CID }` instead of just `CID`

### Features

* support paths in @helia/ipns ([#410](https://github.com/ipfs/helia/issues/410)) ([ca8d5eb](https://github.com/ipfs/helia/commit/ca8d5ebdf587574c7fb84517b558226c3479caa9))


### Dependencies

* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^2.0.0 to ^2.0.1
    * @helia/http bumped from ^1.0.0 to ^1.0.1
    * @helia/ipns bumped from ^5.0.0 to ^6.0.0
    * helia bumped from ^4.0.0 to ^4.0.1

## [4.0.0](https://github.com/ipfs/helia/compare/interop-v3.0.1...interop-v4.0.0) (2024-01-24)


### ⚠ BREAKING CHANGES

* remove gossipsub from default libp2p services ([#401](https://github.com/ipfs/helia/issues/401))
* `helia.routing` is the default routing used, the `libp2p` routing has been removed as it is redundant
* the `libp2p` property has been removed from the `Helia` interface in `@helia/interface` - it is still present on the return type of `createHelia` from the `helia` module

### Features

* add @helia/http to monorepo ([#372](https://github.com/ipfs/helia/issues/372)) ([76220cd](https://github.com/ipfs/helia/commit/76220cd5adf45af7fa61fd0a1321de4722b744d6))
* export binary from @helia/interop ([#384](https://github.com/ipfs/helia/issues/384)) ([3477b27](https://github.com/ipfs/helia/commit/3477b2748d44a862e8afeae1a7a2668cdd8a7100))
* use helia router for IPNS put/get ([#387](https://github.com/ipfs/helia/issues/387)) ([ce74026](https://github.com/ipfs/helia/commit/ce740268e83f50e6f144b74969a98d54005cd852))


### Bug Fixes

* include aegir config in interop and run from install dir ([#389](https://github.com/ipfs/helia/issues/389)) ([a2229bd](https://github.com/ipfs/helia/commit/a2229bd79d5c8b805604bb24bad222462a9ed8cc))
* remove gossipsub from default libp2p services ([#401](https://github.com/ipfs/helia/issues/401)) ([99c94f4](https://github.com/ipfs/helia/commit/99c94f4b85c4ed826a6195207e3545cbbc87a6d1))
* update ipns module to v9 and fix double verification of records ([#396](https://github.com/ipfs/helia/issues/396)) ([f2853f8](https://github.com/ipfs/helia/commit/f2853f8bd5bdcee8ab7a685355b0be47f29620e0))


### Dependencies

* bump kubo from 0.25.0 to 0.26.0 ([#400](https://github.com/ipfs/helia/issues/400)) ([a9c55f0](https://github.com/ipfs/helia/commit/a9c55f0e672e439cbcc6b938963ab150997c6e45))
* The following workspace dependencies were updated
  * dependencies
    * @helia/block-brokers bumped from ^1.0.0 to ^2.0.0
    * @helia/car bumped from ^2.0.1 to ^3.0.0
    * @helia/dag-cbor bumped from ^2.0.1 to ^3.0.0
    * @helia/dag-json bumped from ^2.0.1 to ^3.0.0
    * @helia/http bumped from ^0.9.0 to ^1.0.0
    * @helia/interface bumped from ^3.0.1 to ^4.0.0
    * @helia/ipns bumped from ^4.0.0 to ^5.0.0
    * @helia/json bumped from ^2.0.1 to ^3.0.0
    * @helia/mfs bumped from ^2.0.1 to ^3.0.0
    * @helia/routers bumped from ^0.0.0 to ^1.0.0
    * @helia/strings bumped from ^2.0.1 to ^3.0.0
    * @helia/unixfs bumped from ^2.0.1 to ^3.0.0
    * helia bumped from ^3.0.1 to ^4.0.0

## [3.0.1](https://github.com/ipfs/helia/compare/interop-v3.0.0...interop-v3.0.1) (2024-01-16)


### Bug Fixes

* update type import path ([#379](https://github.com/ipfs/helia/issues/379)) ([ece384a](https://github.com/ipfs/helia/commit/ece384aab5e1c95857aa4aa07b86656710d8ca35))

## [3.0.0](https://github.com/ipfs/helia/compare/interop-v2.0.0...interop-v3.0.0) (2024-01-09)


### ⚠ BREAKING CHANGES

* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3
* uses multiformats v13 and helia v3, renames `dht` routing to `libp2p`
* uses multiformats v13
* uses multiformats v13 and helia v3

### Features

* update helia to v3 and multiformats to v13 ([9f7dc0a](https://github.com/ipfs/helia/commit/9f7dc0a0581524531501fc062fefb6ba26d99c02))
* update helia to v3 and multiformats to v13 ([#147](https://github.com/ipfs/helia/issues/147)) ([001247c](https://github.com/ipfs/helia/commit/001247c6fc38ff3d810736371de901e5e1099f26))
* update helia to v3 and multiformats to v13 ([#167](https://github.com/ipfs/helia/issues/167)) ([a0381b9](https://github.com/ipfs/helia/commit/a0381b95051bbf3edfa4f53e0ae2d5f43c1e4382))
* update helia to v3 and multiformats to v13 ([#45](https://github.com/ipfs/helia/issues/45)) ([f078447](https://github.com/ipfs/helia/commit/f078447b6eba4c3d404d62bb930757aa1c0efe74))
* update helia to v3 and multiformats to v13 ([#45](https://github.com/ipfs/helia/issues/45)) ([3c7d9d4](https://github.com/ipfs/helia/commit/3c7d9d4a8e74e1a808c265fbc6ecbdc24f0f3da9))
* update helia to v3 and multiformats to v13 ([#46](https://github.com/ipfs/helia/issues/46)) ([e3dc586](https://github.com/ipfs/helia/commit/e3dc5867ffc4de0dd3b05b56eb1b0ce98d50dcb1))
* update helia to v3 and multiformats to v13 ([#52](https://github.com/ipfs/helia/issues/52)) ([6405c34](https://github.com/ipfs/helia/commit/6405c3487879614dc4dd7308b15c946d644e0488))
* update helia to v3 and multiformats to v13 ([#87](https://github.com/ipfs/helia/issues/87)) ([ae7cbc9](https://github.com/ipfs/helia/commit/ae7cbc9a16a267cb0f6d7cecd381f919430afaea))


### Bug Fixes

* create @helia/block-brokers package ([#341](https://github.com/ipfs/helia/issues/341)) ([#342](https://github.com/ipfs/helia/issues/342)) ([2979147](https://github.com/ipfs/helia/commit/297914756fa06dc0c28890a2654d1159d16689c2))


### Dependencies

* The following workspace dependencies were updated
  * devDependencies
    * @helia/block-brokers bumped from ~0.0.0 to ~1.0.0
    * @helia/car bumped from ^2.0.0 to ^2.0.1
    * @helia/dag-cbor bumped from ^2.0.0 to ^2.0.1
    * @helia/dag-json bumped from ^2.0.0 to ^2.0.1
    * @helia/interface bumped from ^3.0.0 to ^3.0.1
    * @helia/json bumped from ^2.0.0 to ^2.0.1
    * @helia/mfs bumped from ^2.0.0 to ^2.0.1
    * @helia/strings bumped from ^2.0.0 to ^2.0.1
    * @helia/unixfs bumped from ^2.0.0 to ^2.0.1
    * helia bumped from ^3.0.0 to ^3.0.1

## [2.0.0](https://github.com/ipfs/helia/compare/interop-v1.1.0...interop-v2.0.0) (2024-01-07)


### ⚠ BREAKING CHANGES

* `helia.pin.add` and `helia.pin.rm` now return `AsyncGenerator<CID>`
* The libp2p API has changed in a couple of places - please see the [upgrade guide](https://github.com/libp2p/js-libp2p/blob/main/doc/migrations/v0.46-v1.0.0.md)

### deps

* updates to libp2p v1 ([#320](https://github.com/ipfs/helia/issues/320)) ([635d7a2](https://github.com/ipfs/helia/commit/635d7a2938111ccc53f8defbd9b8f8f8ea3e8e6a))


### Features

* iterable pinning ([#231](https://github.com/ipfs/helia/issues/231)) ([c15c774](https://github.com/ipfs/helia/commit/c15c7749294d3d4aea5aef70544d088250336798))


### Dependencies

* The following workspace dependencies were updated
  * devDependencies
    * @helia/interface bumped from ^2.1.0 to ^3.0.0
    * helia bumped from ^2.1.0 to ^3.0.0

## [1.1.0](https://www.github.com/ipfs/helia/compare/interop-v1.0.3...interop-v1.1.0) (2023-11-06)


### Features

* GatewayBlockBroker prioritizes & tries all gateways ([#281](https://www.github.com/ipfs/helia/issues/281)) ([9bad21b](https://www.github.com/ipfs/helia/commit/9bad21bd59fe6d1ba4a137db5a46bd2ead5238c3))


### Dependencies

* The following workspace dependencies were updated
  * devDependencies
    * @helia/interface bumped from ^2.0.0 to ^2.1.0
    * helia bumped from ^2.0.3 to ^2.1.0

### [1.0.3](https://www.github.com/ipfs/helia/compare/interop-v1.0.2...interop-v1.0.3) (2023-09-18)


### Dependencies

* The following workspace dependencies were updated
  * devDependencies
    * helia bumped from ^2.0.2 to ^2.0.3

### [1.0.2](https://www.github.com/ipfs/helia/compare/interop-v1.0.1...interop-v1.0.2) (2023-09-14)


### Bug Fixes

* **kubo:** ⬆️ Upgrading go-ipfs to kubo ([#251](https://www.github.com/ipfs/helia/issues/251)) ([963a7a2](https://www.github.com/ipfs/helia/commit/963a7a21774703a105c865a5b6db670f278eec73))


### Dependencies

* The following workspace dependencies were updated
  * devDependencies
    * helia bumped from ^2.0.1 to ^2.0.2

### [1.0.1](https://www.github.com/ipfs/helia/compare/interop-v1.0.0...interop-v1.0.1) (2023-08-16)


### Bug Fixes

* enable dcutr by default ([#239](https://www.github.com/ipfs/helia/issues/239)) ([7431f09](https://www.github.com/ipfs/helia/commit/7431f09aef332dc142a5f7c2c59c9410e4529a92))


### Dependencies

* The following workspace dependencies were updated
  * devDependencies
    * helia bumped from ^2.0.0 to ^2.0.1

## [1.0.0](https://www.github.com/ipfs/helia/compare/interop-v0.0.0...interop-v1.0.0) (2023-08-16)


### ⚠ BREAKING CHANGES

* libp2p has been updated to 0.46.x

### Dependencies

* **dev:** bump go-ipfs from 0.21.0 to 0.22.0 ([#228](https://www.github.com/ipfs/helia/issues/228)) ([2e8e447](https://www.github.com/ipfs/helia/commit/2e8e447f782745e517e935cd1bb3312db6384a5b))
* update libp2p to 0.46.x ([#215](https://www.github.com/ipfs/helia/issues/215)) ([65b68f0](https://www.github.com/ipfs/helia/commit/65b68f071d04d2f6f0fcf35938b146706b1a3cd0))



### Dependencies

* The following workspace dependencies were updated
  * devDependencies
    * @helia/interface bumped from ^1.0.0 to ^2.0.0
    * helia bumped from ^1.0.0 to ^2.0.0
