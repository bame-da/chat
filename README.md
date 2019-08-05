# On MacOS

## Requirements:

1. Homebrew (https://brew.sh/)
1. Stack, OpenSSL and c-ares (`brew install haskell-stack openssl c-ares`)
1. Working DAML Dev Env (https://github.com/digital-asset/daml)
1. gRPC v1.2.2 (https://github.com/grpc/grpc/blob/v1.22.x/BUILDING.md). Don't forget to check out the tag before building!
1. Compiled Haskell Bindings (https://github.com/digital-asset/daml/tree/master/language-support/hs/bindings)
1. Installed DAML SDK (https://docs.daml.com/getting-started/installation.html)

## Building

1. Copy the compiled bindings into the folder `lib`
2. Build with `stack build`


# Running

1. Start Sandbox with `daml sandbox`
2. Start chat clients with `stack run chat-exe -- Alice`,  `stack run chat-exe -- Bob` and similar


## Chat as Alice

    Alice> :link Bob
    linked: Bob
    Alice> :link Nick
    linked: Nick
    Alice> ?
    [Bob,Nick]
    Alice> Hey to both of you

## Chat as Dave

    Dave> :link Edwina
    linked: Edwina
    Dave> ?
    Edwina

## Chat as Bob

    linked: Alice
    linked: Nick
    Bob> ?
    [Alice,Nick]
    Bob> :link Dave
    linked: Dave
    linked: Edwina
    Bob> ?
    [Alice,Nick,Dave,Edwina]
    Bob> Hey everyone

## Chat as Nick

    linked: Alice
    linked: Bob
    linked: Dave
    linked: Edwina
    Nick> ?
    [Alice,Bob,Dave,Edwina]
    Nick> Morning everybody
    Nick> !Alice
    Nick> (Alice) Who are Dave and Edwina?
