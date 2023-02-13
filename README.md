# building-ctf-challenges

Some templates and information on how to contribute to our events, and build challenges.

## Challenge Creation Templates

See examples within this repository on how to structure challenge files and what kind of information is needed. This information may change as the underlying hosting service (e.g., CTFd) evolves but many of the concepts will be the same.

## General Guidelines

1. Each challenge should have a fairly simple "path" through the solve.
    a. Each step should have indicators and be explainable
    b. Challenges shouldn't have big jumps between steps
    c. You should be able to explain how you could go about solving it without requiring "insider" knowledge.
2. Challenges are there to help people learn topics useful in cybersecurity and hacking.
    a. Although we do want to "odd-ball" challenges and love to see them, the majority of the challenges should be relatable back to the audience.
    b. Super complicated challenges are exciting and fun to walk through but many won't solve them.
    c. Challenges are for the participants, not the creators.
3. Depending on the event, there WILL be exceptions to these guidelines...
    a. Stay tuned in the Discord channels for an event to see what the goals are for the participants.

## Challenge Formats

We typically see three types of challenges:

1. Question and Answer
2. File Download
3. Container Challenges

### Question and Answer

Challenge doesn't have any specific files associated with it. Some examples are:

- Trivia
- OSINT
- Riddles
- Cryptography with challenge in description

### File Download

Challenges that are solved with some sort of download. Some examples are:

- Challenge that is found within a self-contained file
- PCAPS
- Cryptography challenges with encrypted file
- Zips
- Reverse engineering
- File images
- Stego

### Container Challenges

Challenges that have a service running in a container. These can also be associated with file downloads if that file is associated with the challenge. Some examples are:

- Web exploit challenges
- Binary exploit challenges (with or without exe downloads for reversing)
- Other challenge types hosted in web server that outputs a flag
- Protocol attacks using the container as the host/server/client/etc.

NOTE: With our current infrastructure and use of CTFd, each docker challenge must only expose a single port. For more information, please see the requirements around docker challenges found at: https://github.com/offsecginger/CTFd-Docker-Challenges

## Challenge File Requirements

We are currently using the CTFd CLI requirements in order to leverage CTFd as the underlying platform. This specification is defined at the URL below:

`https://github.com/CTFd/ctfcli/blob/master/ctfcli/spec/challenge-example.yml`

For more information check out the CTFd docs or throw a message in our Discord.

- `https://docs.ctfd.io/docs/challenges/overview`

## Flag Format

Our events currently follow the standard format of `TPZ{<insert flag>}`. This is the basic flag format--the letters "TPZ" followed by the flag in curly braces. If the flag deviates from this format, it should be mentioned in the challenges description or the flag with the markers should be allowed as a solution. Meaning, if the answer to a question is "ANSWER" and the challenge does not specify that it has a non-standard answer, you should accept both "ANSWER" and "TPZ{ANSWER}".

The flag should be comprised of printable ASCII characters and it's helpful to have a human-readable flag. This makes it obvious that the flag was found when the challenge was solved and helps drive some confidence around processes.

As a general rule, the format of the flag shouldn't be the challenge.

### Using the Flag Format as a Hint

If the format follows the convention, this can be used as part of the challenge. If we know the flag starts with TPZ, and it is a cryptography challenge, we could leverage that information as part of the known plaintext.
