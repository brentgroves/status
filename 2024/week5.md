# week5

## Father's direction

My son finish installing and testing the API gateway and remember all results are in my hands.  What seems like failures are not.  These seeming failures are all apart of my plan to create in you a "loving heart."

I love you my son and know all that you are going through. I am with you and have a plan for this day. Take courage you have nothing to fear because I am with you. Have hope my son I have many wonderful things for you to look forward to. I will revive your spirit and guide you every step of the way my son.

Trust me to take care of you my son.  Do not fear anything because I am always here to take care of you.  You will go through many trials both hard and difficult but fear not.  These troubles are necessary for you to grow to be the man I want you to be.

## service mesh vs. API gateway

Here are the key things to know about service mesh vs. API gateway:

- Service mesh acts as a centralized infrastructure layer for efficient microservices communication, simplifying tasks like service discovery and load balancing.
- API gateways, on the other hand, serves as the entry point for external clients to access microservices, managing functions like request routing and authentication.

## API gateway

- Continus installing and testing the API gateway
- Then test the k8s API gateway by following the instructions at Kong Academy's **[API Transformations Plugins and decK](https://education.konghq.com/dashboard)** tutorial and/or **[jq plugin tutorial](https://docs.konghq.com/hub/kong-inc/jq/how-to/basic-example/)**.

## Kong academy

Kong Academy is a great training environment for its API Gateway. Here is its **[training catalog](https://education.konghq.com/catalog)**

## **[Embedding Lua in Go](https://otm.github.io/2015/07/embedding-lua-in-go/)**

Command line parameters, environment variables, and configuration files are common ways to change the behavior of software. However, sometimes that is just not enough and an embedded language can be the solution. In this case we will embed Lua using gopher-lua.

```go
package main

import "github.com/yuin/gopher-lua"

func main() {
  L := lua.NewState()
  defer L.Close()
  if err := L.DoString(`print("Hello World")`); err != nil {
    panic(err)
  }
}
```

lua.NewState() creates our Lua VM, and it is though L (*lua.LState) we will interact with Lua in the future. Throughout the post L will denote a pointer to lua.LState. L.DoString runs the Lua code in the VM. Running the Go code will yield:

```bash
$ go run hello.go
Hello World
```

## Migration

- get password
Office 365
<bgroves@buschegroup.com>
JesusLives1!
<Bgroves@mobexglobal.com>
Office 365  
<bgroves@buschegroup.com>  
JesusLives1!  
<Bgroves@mobexglobal.com>  
Spirit1$! - Nov 21,2023
Messiah2!$ - previous

UserName:  <bGroves@linamar.com>
Password:
L1n@ALB2023!053

Linamar Email Address:  <Brent.Groves@linamar.com>

### fork Azure repos

```bash
git@ssh.dev.azure.com:v3/MobexGlobal/MobexCloudPlatform/Reporting
git@ssh.dev.azure.com:v3/MobexGlobal/MobexCloudPlatform/mobexsql
git@ssh.dev.azure.com:v3/MobexGlobal/ReportBuilder/TrialBalance
trial_balance_powerbi
```

### Update git scripts

- startday-old.sh
- pull new repos to dev machines

### PowerBI

- License of PowerBI and PowerBI paginated reports

### Power BI Report Builder

- Publish Trial Balance to teams tab

## **[Multipass](https://multipass.run/docs)** Documentation

Multipass is a tool to generate cloud-style Ubuntu VMs quickly on Linux, macOS, and Windows.

It gives you a simple but powerful CLI that allows you to quickly access an Ubuntu command line or create your own local mini-cloud.

Local development and testing is a pain, but Multipass makes it easier by automating all of your setup and teardown. Multipass has a growing library of images that give you the ability to launch purpose-built VMs, or custom VMs you’ve configured yourself through its powerful cloud-init interface.

Developers can use Multipass to prototype cloud deployments and to create fresh, customized Linux dev environments on any machine. Mac and Windows users can use Multipass as the quickest way to get an Ubuntu command line on their system. New Ubuntu users can use it as a sandbox to try new things without affecting their host machine, and without the need to dual boot.
