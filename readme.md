# CI-CD Handbook

Long title could be:
> How to set up a semi-professional cloud to develop and deploy microservices

On this handbook, we will describe how to set and run an environment to quickly deploy and run your microservices on a semi-professional cloud.

The tools used for this handbook are:
 
- Kubernetes
- gitea
- woodpecker-ci
- docker
- terraform


# mdbook

This book is being written using `mdbook`.
it is needed to build and serve the book locally.

### Install vía cargo

`mdbook` can be installed using cargo, if it is present on your system. 
Cargo can be installed vía the official rust tool `rustup`.

If you already have cargo on your system, just 
`cargo install mdbook`

### Install via brew

As an alternative, you can use brew package manager too, as simple as:
`brew install mdbook`

# Run the book locally

*mdbook* will serve the book as html in your system on the port 3000 by default.

Just run: 
`mdbook watch`




