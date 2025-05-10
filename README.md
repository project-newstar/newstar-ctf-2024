# NewStar CTF 2024

This repository is the archive of [NewStar CTF 2024](https://newstar.wiki/guide/2024/).

You can view the challenge details in each `week?` directory:

- [Week 1](./week1)
- [Week 2](./week2)
- [Week 3](./week3)
- [Week 4](./week4)
- [Week 5](./week5)

You can download challenge images at [openctf/newstar-2024](https://hub.docker.com/r/openctf/newstar-2024) on Docker Hub.

You can download challenge attachments at [Github Release](https://github.com/project-newstar/newstar-ctf-2024/releases/tag/attachment) page of this repository.

## Metapack

All the metadata, images, attachments of challenges, are presented at [metapack.json](./metapack.json).

It has the following structure:

```typescript
interface Metadata {
  id: number;
  name: string;
  description: string;
  category: string[];
  author: string;
  tags: string[];
  attachment: string[];
  environment: {
    image: string;     // remote image url, can use `docker pull` to download
    ports: number[];   // ports to be exposed in the container
    type: "tcp" | "http"
  }[];
  flag: string | null; // `null` means dynamic flag
}[];

type Metapack = Metadata[];
```

> [!IMPORTANT]
> Dynamic flag requires you to pass environment variables `ICQ_FLAG` to the container when starting it.

The manifest file may help you to deploy the whole CTF game on your system.

## License

All authors of challenges can be found at [AUTHORS](./AUTHORS).

Copyright (c) NewStar CTF 2024. All rights reserved.

Licensed under the [MIT License](./LICENSE).
