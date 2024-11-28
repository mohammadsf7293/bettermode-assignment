## Description

This is a project which is about creating a simple twitter (X) server application.
The project has mostly focused on implementing a permission system like that of twitter.
The permission system is like this:
We want the author of the tweet to be able to set a series of permissions for their tweet. By default, a tweet inherits parent tweet permission, if the tweet has no parent, then it is accessible to everyone and only the author can edit the tweet. Here is the list of permissions:

- **View**: Author can add users or groups to the “View” permission list, if someone is in this list or is part of a group that is in this list, can see the tweet. Others can’t.
  - If the tweet is a reply to another tweet, the author can decide to enable “auto-inheritance” which makes sure the view permissions of this tweet are identical to the parent tweet. Any changes on the parent tweet’s view permissions will be reflected in this tweet as well.
- **Edit**: Author can add users or groups to the “Edit” permission list, if someone is in this list or is part of a group that is in this list, can edit the tweet. Others can’t.
  - If the tweet is a reply to another tweet, the author can decide to enable “auto-inheritance” which makes sure the edit permissions of this tweet is identical to the parent tweet. Any changes to the parent tweet’s edit permissions will be reflected in this tweet as well.
-

# Scalability of Project Architecture (System Design)

<p align="center">
 <img src="https://ipfs.io/ipfs/Qmee9c6QApMcrHuivmBWWYVxK3CKveLSTENLQvtutjTDie" style="width:25vw;" alt="Better Mode architecture" />
</p>

As you see from the diagram above, a cache mediator is used which is Redis.
Redis is used in order to dramatically decrease the traffic directing MySQL servers.
If something is not found in the cache, then it will be searched through MySQL Database

# Cache strcuture

## Project setup

```bash
yarn install
```

## Compile and run the project

```bash
# development
$ yarn run start

# watch mode
$ yarn run start:dev

# production mode
$ yarn run start:prod
```

## Run tests

```bash
# unit tests
$ yarn run test

# e2e tests
$ yarn run test:e2e

# test coverage
$ yarn run test:cov
```

## Deployment

When you're ready to deploy your NestJS application to production, there are some key steps you can take to ensure it runs as efficiently as possible. Check out the [deployment documentation](https://docs.nestjs.com/deployment) for more information.

If you are looking for a cloud-based platform to deploy your NestJS application, check out [Mau](https://mau.nestjs.com), our official platform for deploying NestJS applications on AWS. Mau makes deployment straightforward and fast, requiring just a few simple steps:

```bash
yarn install -g mau
mau deploy
```

With Mau, you can deploy your application in just a few clicks, allowing you to focus on building features rather than managing infrastructure.

## Resources

Check out a few resources that may come in handy when working with NestJS:

- Visit the [NestJS Documentation](https://docs.nestjs.com) to learn more about the framework.
- For questions and support, please visit our [Discord channel](https://discord.gg/G7Qnnhy).
- To dive deeper and get more hands-on experience, check out our official video [courses](https://courses.nestjs.com/).
- Deploy your application to AWS with the help of [NestJS Mau](https://mau.nestjs.com) in just a few clicks.
- Visualize your application graph and interact with the NestJS application in real-time using [NestJS Devtools](https://devtools.nestjs.com).
- Need help with your project (part-time to full-time)? Check out our official [enterprise support](https://enterprise.nestjs.com).
- To stay in the loop and get updates, follow us on [X](https://x.com/nestframework) and [LinkedIn](https://linkedin.com/company/nestjs).
- Looking for a job, or have a job to offer? Check out our official [Jobs board](https://jobs.nestjs.com).

## Support

Nest is an MIT-licensed open source project. It can grow thanks to the sponsors and support by the amazing backers. If you'd like to join them, please [read more here](https://docs.nestjs.com/support).

## Stay in touch

- Author - [Kamil Myśliwiec](https://twitter.com/kammysliwiec)
- Website - [https://nestjs.com](https://nestjs.com/)
- Twitter - [@nestframework](https://twitter.com/nestframework)

## License

Nest is [MIT licensed](https://github.com/nestjs/nest/blob/master/LICENSE).
