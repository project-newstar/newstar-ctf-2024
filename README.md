# NewStar CTF 2024

This repository is the archive of [NewStar CTF 2024](https://newstar.wiki/guide/2024/). Attachments and images of challenges are also part of the repository.

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
  id: number | string; // must be unique
  name: string;
  description: string;
  category: string[];  // sorted based on hierarchical relationship
  tags: string[];
  author: string;
  attachments: string[];
  services: {
    image: string;     // remote image url, can use `docker pull` to download
    ports: number[];   // ports to be exposed in the container
    type: "tcp" | "http"
  }[];
  flag: string | null; // `null` means dynamic flag
  // extra fields, can be customized according to specific needs
  extra?: Record<string, any>;
}[];

type Metapack = Metadata[];
```

> [!IMPORTANT]
> Dynamic flag requires you to pass environment variables `ICQ_FLAG` to the container when starting it.

The *metapack* file may help you to deploy the whole CTF game on your system.

## Credits and License

All authors of challenges can be found at [AUTHORS](./AUTHORS).

Copyright (c) Authors of NewStar CTF 2024, Beijing integrity technology co., Ltd. (a.k.a. ichunqiu). All rights reserved, independently for each author.

Distribution of text document follows [CC BY-SA 4.0](https://creativecommons.org/licenses/by-sa/4.0/). Challenge related codes, attachments, images, etc. are licensed under [LGPL 3.0](./LICENSE). Unless otherwise specified.

You can directly use them for non-profit purposes without any modification. Charged distribution of them is not allowed if not permitted.

## Additional Notes

So-called *image(s)* in this document refers to things like virtual machine images, docker images, etc. It does not refer to images in the sense of pictures.

The correspondence between the author's ID and real-name information will not be made public. The copyright subject has the right of interpretation of it.
