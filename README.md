# deadqueuemv

Move all messages from one SQS queue, to another.

## Installation

    go get github.com/Freniz/deadqueuemv


## Configuration

export AWS_SECRET_ACCESS_KEY=xxxxxxxxx
export AWS_ACCESS_KEY_ID=xxxxxxx
export AWS_REGION=eu-xxxx-1



## Usage

Supply source and destination URL endpoints.

    deadqueuemv -src https://eu-xxxx-1.queue.amazonaws.com/abc/queueA -dest https://eu-xxxx-1.queue.amazonaws.com/abc/queueB



Create some SQS messages to play with using the AWS CLI.

    for i in {0..24..1}; do
        aws sqs send-message \
            --queue-url https://ap-southeast-2.queue.amazonaws.com/123/wat-a
            --message-body "{\"id\": $i}"
    done
