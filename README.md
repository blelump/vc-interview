# Python SSI interview

A test project for a SSI Backend Developer position.

## Overview

SSI movement yields a bunch of new buzzwords that are essential to understand in order to be able to smoothly walk around the technology underneath. This is also a pre-challenge task to accomplish. 

SSI engages several parties (actors) to provide the truly decentralized and trustful network. Actually there at least a few approaches how to tackle the "trust" problem, but let's focus here on the classic model, where there are three essential roles: Issuer, Holder and Verifier and the Verifiable Data Registry that serves as a source of trust. See also https://www.w3.org/TR/vc-data-model/#roles .

A very well introduction to the concept can be found here: https://vimeo.com/459347107#t=520s .

## Features / requirements

Let's try to mimic a part of this network and implement an Issuer and a Verifiable Data Registry. The basic features of this task would be to:

* Get acquainted with the SSI core concepts to get the big picture;
* Use LibSodium (you may use `pysodium`) in order to generate ED25119 key pair; Use `py-multibase` for Base58 encoding;
* Use the generated public key and generate [DID's and store its DID-document](https://www.w3.org/TR/did-core/) counterpart in a Verifiable Data Registry. Assume it is a HTTP service. Choose whatever storage method you will find suitable to store JSON documents (may be even a file on disk as long as you will be able to resolve DID document for given DID). The Verifiable Data Registry should expose two endpoints over HTTP protocol: `GET /did/DID` and `POST /did` with a body (DID document);
* Assume DID-document has the following shape: https://www.w3.org/TR/did-core/#example-13-example-verification-methods;
* Generate DID for the DID document -- here you may follow the `did:sov` [rules](https://sovrin-foundation.github.io/sovrin/spec/did-method-spec-template.html#namespace-specific-identifier-nsi);
* Implement similar scenario to the one given [here](https://www.w3.org/TR/vc-data-model/#example-1-a-simple-example-of-a-verifiable-credential) so there is an Issuer (who in this case is an University) that issues the Verifable Credential (saying that someone has graduated from this University);
* Assume some DID for the Holder and use his DID in the VC above;
* Sign Verifable Credential with the private key you have generated in the previous step;
* Do not implement Holder, but instead, upload the VC from previous step into some place, ie. a gist or whatever you will find suitable for this purpose (this is essentially an oversimplification of the Holder role in this network, but let's keep the use case simple);

## Caveats

Since it's more a concept app, it’s perfectly fine to make some compromises:

you can use whatever technology/framework is suitable for you (yet, please don't use a sledgehammer to crack a nut), the only interesing part is the enduser is able to run it and see the result;
Don't be neither too generic nor too specific – don't polish it too much, but also keep focus on the code as well – your final product should be „just enough”.

If you don't feel prepared for the job, either get familiar with languages/technologies you'd consider useful here, or let us know you're not ready for it;

Your work should be available via GitHub as a public repository, [commit often](https://chris.beams.io/posts/git-commit/).

Value quality over quantity. And, finally, when in doubt – especially about the scope of the task – feel free to ask.
