# SSH Key Setup

## Github

1. Run the following from a machine with ssh-keygen installed `ssh-keygen -t rsa -b 4096 -C "camfurbush@gmail.com"`
2. Run the following to get the contents of the publickey `cat /home/camfurbush/.ssh/id_rsa.pub`
3. Copy and upload to github/gitlab
4. Copy the id_rsa.pub and id_rsa from the linux machine to your windows folder
5. Add the following to your ~/.ssh/config file

    ```sh
    Host 192.168.1.29
      Port 822
    ```

## Troubleshooting

`ssh -Tv git@192.168.1.29`