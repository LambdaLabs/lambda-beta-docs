---
title: "How do I get started using the Firewall feature?"
type: docs
tags:
- network
- SSH
---

The [Firewall feature](https://cloud.lambdalabs.com/firewall) allows you to
configure firewall rules to restrict incoming connections to your instances.

{{% alert title="Note" color="info" %}}
Firewall rules configured using the Firewall feature apply to all of your
instances outside of the Texas, USA (us-south-1) region.
{{% /alert %}}

To use the Firewall feature:

1. Click **Firewall** in the left sidebar of the dashboard to open your
   firewall settings.

   {{< imgproc firewall-settings Resize "400x" >}}{{< /imgproc >}}

   Under **General Settings**, use the toggle next to **Allow ICMP traffic
   (ping)** to allow or restrict incoming ICMP traffic to your instances.

   {{% alert title="Note" color="info" %}}
   For network diagnostic tools such as `ping` and `mtr` to be able to reach
   your instances, you need to allow incoming ICMP traffic.
   {{% /alert %}}

1. Next to **Inbound Rules**, click **Edit** to configure incoming TCP and UDP
   traffic rules.

   {{< imgproc inbound-rules Resize "400x" >}}{{< /imgproc >}}

   Set the **Protocol**, **Port range**, and **Source** for the rule you want
   to add or modify. Use the **Description** field to specify the purpose of
   the rule.

   - **Protocol** can be **All** (both TCP and UDP), **TCP**, or **UDP**.

     - Most services, such as web servers and mail servers, use TCP.
     - Some services, such as OpenVPN (by default), use UDP.

   {{% alert title="Tip" color="success" %}}
   In most cases, it's safe to set **Protocol** to **All**.
   {{% /alert %}}

   - **Port range** can be:

     - A single port, for example, `8080`.
     - A range of ports, for example, `8080-8081`.

   {{% alert title="Warning" color="warning" %}}
   If you don't have a rule to allow incoming traffic to port TCP/22, **you won't
   be able to access your instances using SSH**.
   {{% /alert %}}

   - **Source** can be:

     - A single IP address, for example, `203.0.113.1`.
     - A range of IP addresses in CIDR notation, for example, `203.0.113.0/24`.

   {{% alert title="Tip" color="success" %}}
   To allow incoming traffic from any source, set **Source** to `0.0.0.0/0`.
   {{% /alert %}}

   {{% alert title="Tip" color="success" %}}
   To allow incoming traffic only from your computer:

   1. Learn your public IP address by visiting
      [What Is My IP Address](https://ifconfig.me/).

      **Note:** On most home networks, all computers and devices share the
      same public IP address, even though they all have a unique private IP
      address.

      Also, most home networks have a dynamically assigned public IP address,
      meaning the IP address can change. If your public IP address changes,
      you'll need to update your firewall rule.

   1. Set **Source** to your public IP address.
   {{% /alert %}}

1. Click **Add rule** to add additional rules, if you have any to add.

   Click the <span style="color:red;font-weight:bold">x</span> next to any rule you want to delete.

1. Once you're finished adding and modifying rules, click **Update** to apply
   your changes.
