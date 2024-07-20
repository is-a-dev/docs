# How to Create a Custom Email

This guide is designed for beginners. If you're already familiar with some basics, you might be able to skip certain pre-requisites and steps.

### Pre-requisites
Before you begin, make sure you have the following:
- **Discord Account**: For accessing our official bot and community.
- **Gmail Account**: For receiving forwarded emails.
- **ImprovMX Account**: For email forwarding services.
- **Cloudflare Account**: For managing DNS records.
- **is-a.dev Domain Name**: Your custom domain for email.

# Step One: Set Up Your Domain

1. **Create Your Custom Domain**:
   - **Access our Discord**: Join our official [Discord server]() if you haven’t already. You will need this to interact with our official bot.
   - **Run a Command**: Use the provided command in the Discord bot to create your custom domain. This process will guide you through the setup.

2. **Set Up Cloudflare**:
   - **Sign Up or Log In**: Go to [Cloudflare](https://www.cloudflare.com/) and create an account or log in if you already have one.
   - **Add Your Domain**: Follow Cloudflare’s prompts to add your newly created domain. Cloudflare will manage your domain’s DNS settings.

   For detailed instructions on setting up Cloudflare and your domain, refer to this [guide](https://www.is-a.dev/docs/cloudflare-pages/).

# Step Two: Set Up ImprovMX

1. **Create an ImprovMX Account**:
   - **Visit ImprovMX**: Go to [ImprovMX](https://improvmx.com/) and click on “Sign Up” to create a new account.
   - **Register Your Domain**: After signing up, log in to your ImprovMX account and add your custom domain to start setting up email forwarding.

2. **Configure ImprovMX**:
   - **Add Email Addresses**: Within ImprovMX, set up the email addresses you want to use (e.g., `info@yourdomain.com`). 
   - **Forward Emails**: Specify the destination email address where you want your emails to be forwarded (e.g., your Gmail account).

   Here’s an example of what the ImprovMX setup page looks like:
   ![ImprovMX Setup Example](https://host-image.is-a.dev/file/c94b335a97ab4af67d8df.jpg)

# Step Three: Update DNS Records on Cloudflare

1. **Log In to Cloudflare**:
   - Go to the Cloudflare dashboard and select your domain.

2. **Add DNS Records**:
   - **Access DNS Settings**: Find and go to the DNS settings for your domain.
   - **Add MX Records**: ImprovMX will provide you with MX records. Add these records in Cloudflare to direct your email traffic to ImprovMX.
   - **Add TXT Records**: If ImprovMX provides TXT records for domain verification, add these as well.

   Follow these steps in Cloudflare:
   - Click “Add Record”.
   - Choose the type of record (MX or TXT).
   - Enter the details provided by ImprovMX.
   - Save your changes.

3. **Verify DNS Records**:
   - **Check ImprovMX**: ImprovMX may ask you to verify that the DNS records are correctly set up. This verification process may take some time due to DNS propagation.

# Step Four: Test Your Email

1. **Send a Test Email**:
   - Send an email to your new custom email address to check if it is properly forwarded to your Gmail account.

2. **Troubleshoot If Needed**:
   - If emails are not forwarding as expected, double-check your ImprovMX and Cloudflare settings to ensure all records are correctly configured.

Congratulations! You’ve set up your custom email. If you run into any issues or need help, feel free to ask for support in our Discord community.
