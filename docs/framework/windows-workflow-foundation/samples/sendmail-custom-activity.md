---
description: '자세한 정보: SendMail 사용자 지정 작업'
title: SendMail 사용자 지정 활동
ms.date: 03/30/2017
ms.assetid: 947a9ae6-379c-43a3-9cd5-87f573a5739f
ms.openlocfilehash: 853e28d26c41338670d377593d5a3536b011d112
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741759"
---
# <a name="sendmail-custom-activity"></a><span data-ttu-id="51e52-103">SendMail 사용자 지정 활동</span><span class="sxs-lookup"><span data-stu-id="51e52-103">SendMail Custom Activity</span></span>

<span data-ttu-id="51e52-104">이 샘플에서는 워크플로 애플리케이션 내에서 사용하기 위해 <xref:System.Activities.AsyncCodeActivity>로부터 파생되는 사용자 지정 활동을 만들어 SMTP를 사용하여 메일을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-104">This sample demonstrates how to create a custom activity that derives from <xref:System.Activities.AsyncCodeActivity> to send mail using SMTP for use within a workflow application.</span></span> <span data-ttu-id="51e52-105">사용자 지정 작업은의 기능을 사용 하 여 <xref:System.Net.Mail.SmtpClient> 비동기적으로 전자 메일을 보내고 인증을 사용 하 여 메일을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-105">The custom activity uses the capabilities of <xref:System.Net.Mail.SmtpClient> to send email asynchronously and to send mail with authentication.</span></span> <span data-ttu-id="51e52-106">또한 테스트 모드, 토큰 바꾸기, 파일 템플릿 및 테스트 드롭 경로와 같은 몇 가지 최종 사용자 기능도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-106">It also provides some end-user features like test mode, token replacement, file templates, and test drop path.</span></span>  
  
 <span data-ttu-id="51e52-107">다음 표에서는 `SendMail` 활동의 인수에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-107">The following table details the arguments for the `SendMail` activity.</span></span>  
  
|<span data-ttu-id="51e52-108">Name</span><span class="sxs-lookup"><span data-stu-id="51e52-108">Name</span></span>|<span data-ttu-id="51e52-109">Type</span><span class="sxs-lookup"><span data-stu-id="51e52-109">Type</span></span>|<span data-ttu-id="51e52-110">설명</span><span class="sxs-lookup"><span data-stu-id="51e52-110">Description</span></span>|  
|-|-|-|  
|<span data-ttu-id="51e52-111">호스트</span><span class="sxs-lookup"><span data-stu-id="51e52-111">Host</span></span>|<span data-ttu-id="51e52-112">String</span><span class="sxs-lookup"><span data-stu-id="51e52-112">String</span></span>|<span data-ttu-id="51e52-113">SMTP 서버 호스트의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-113">Address of the SMTP server host.</span></span>|  
|<span data-ttu-id="51e52-114">포트</span><span class="sxs-lookup"><span data-stu-id="51e52-114">Port</span></span>|<span data-ttu-id="51e52-115">String</span><span class="sxs-lookup"><span data-stu-id="51e52-115">String</span></span>|<span data-ttu-id="51e52-116">호스트에 있는 SMTP 서비스의 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-116">Port of the SMTP service in the host.</span></span>|  
|<span data-ttu-id="51e52-117">EnableSsl</span><span class="sxs-lookup"><span data-stu-id="51e52-117">EnableSsl</span></span>|<span data-ttu-id="51e52-118">bool</span><span class="sxs-lookup"><span data-stu-id="51e52-118">bool</span></span>|<span data-ttu-id="51e52-119"><xref:System.Net.Mail.SmtpClient>에서 SSL(Secure Sockets Layer)을 사용하여 연결을 암호화할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-119">Specifies whether the <xref:System.Net.Mail.SmtpClient> uses Secure Sockets Layer (SSL) to encrypt the connection.</span></span>|  
|<span data-ttu-id="51e52-120">UserName</span><span class="sxs-lookup"><span data-stu-id="51e52-120">UserName</span></span>|<span data-ttu-id="51e52-121">String</span><span class="sxs-lookup"><span data-stu-id="51e52-121">String</span></span>|<span data-ttu-id="51e52-122">보낸 사람의 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 속성을 인증하는 자격 증명을 설정할 사용자 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-122">Username to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="51e52-123">암호</span><span class="sxs-lookup"><span data-stu-id="51e52-123">Password</span></span>|<span data-ttu-id="51e52-124">String</span><span class="sxs-lookup"><span data-stu-id="51e52-124">String</span></span>|<span data-ttu-id="51e52-125">보낸 사람의 <xref:System.Net.Mail.SmtpClient.Credentials%2A> 속성을 인증하는 자격 증명을 설정할 암호입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-125">Password to set up the credentials to authenticate the sender <xref:System.Net.Mail.SmtpClient.Credentials%2A> property.</span></span>|  
|<span data-ttu-id="51e52-126">주체</span><span class="sxs-lookup"><span data-stu-id="51e52-126">Subject</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="51e52-127">메시지 제목입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-127">Subject of the message.</span></span>|  
|<span data-ttu-id="51e52-128">본문</span><span class="sxs-lookup"><span data-stu-id="51e52-128">Body</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="51e52-129">메시지 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-129">Body of the message.</span></span>|  
|<span data-ttu-id="51e52-130">Attachments</span><span class="sxs-lookup"><span data-stu-id="51e52-130">Attachments</span></span>|<xref:System.Activities.InArgument%601>\<string>|<span data-ttu-id="51e52-131">이 전자 메일 메시지에 첨부 된 데이터를 저장 하는 데 사용 되는 첨부 파일 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-131">Attachment collection used to store data attached to this email message.</span></span>|  
|<span data-ttu-id="51e52-132">From</span><span class="sxs-lookup"><span data-stu-id="51e52-132">From</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="51e52-133">이 전자 메일 메시지의 보낸 사람 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-133">From address for this email message.</span></span>|  
|<span data-ttu-id="51e52-134">대상</span><span class="sxs-lookup"><span data-stu-id="51e52-134">To</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="51e52-135">이 전자 메일 메시지의 받는 사람이 들어 있는 주소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-135">Address collection that contains the recipients of this email message.</span></span>|  
|<span data-ttu-id="51e52-136">CC</span><span class="sxs-lookup"><span data-stu-id="51e52-136">CC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="51e52-137">이 전자 메일 메시지에 대 한 CC (참조) 받는 사람이 들어 있는 주소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-137">Address collection that contains the carbon copy (CC) recipients for this email message.</span></span>|  
|<span data-ttu-id="51e52-138">BCC</span><span class="sxs-lookup"><span data-stu-id="51e52-138">BCC</span></span>|<xref:System.Activities.InArgument%601>\<<xref:System.Net.Mail.MailAddressCollection>>|<span data-ttu-id="51e52-139">이 전자 메일 메시지의 BCC (숨은 참조) 받는 사람이 들어 있는 주소 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-139">Address collection that contains the blind carbon copy (BCC) recipients for this email message.</span></span>|  
|<span data-ttu-id="51e52-140">토큰</span><span class="sxs-lookup"><span data-stu-id="51e52-140">Tokens</span></span>|<span data-ttu-id="51e52-141"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span><span class="sxs-lookup"><span data-stu-id="51e52-141"><xref:System.Activities.InArgument%601><IDictionary\<string, string>></span></span>|<span data-ttu-id="51e52-142">본문에서 바꿀 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-142">Tokens to replace in the body.</span></span> <span data-ttu-id="51e52-143">사용자는 이 기능을 통해 나중에 이 속성을 사용하여 제공된 토큰으로 바꿀 수 있는 일부 값을 본문에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-143">This feature allows users to specify some values in the body than can be replaced later by the tokens provided using this property.</span></span>|  
|<span data-ttu-id="51e52-144">BodyTemplateFilePath</span><span class="sxs-lookup"><span data-stu-id="51e52-144">BodyTemplateFilePath</span></span>|<span data-ttu-id="51e52-145">String</span><span class="sxs-lookup"><span data-stu-id="51e52-145">String</span></span>|<span data-ttu-id="51e52-146">본문에 대한 템플릿의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-146">Path of a template for the body.</span></span> <span data-ttu-id="51e52-147">`SendMail` 활동은 이 파일의 내용을 본문 속성에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-147">The `SendMail` activity copies the contents of this file to its body property.</span></span><br /><br /> <span data-ttu-id="51e52-148">템플릿에는 토큰 속성의 내용으로 바뀌는 토큰이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-148">The template can contain tokens that are replaced by the contents of the tokens property.</span></span>|  
|<span data-ttu-id="51e52-149">TestMailTo</span><span class="sxs-lookup"><span data-stu-id="51e52-149">TestMailTo</span></span>|<xref:System.Net.Mail.MailAddress>|<span data-ttu-id="51e52-150">이 속성을 설정 하면 모든 메일이 지정 된 주소로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-150">When this property is set, all emails are sent to the address specified in it.</span></span><br /><br /> <span data-ttu-id="51e52-151">이 속성은 워크플로를 테스트할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-151">This property is intended to be used when testing workflows.</span></span> <span data-ttu-id="51e52-152">예를 들어 실제 받는 사람에 게 전자 메일을 보내지 않고 모든 전자 메일을 보낼지 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-152">For example, when you want to make sure that all emails are sent without sending them to the actual recipients.</span></span>|  
|<span data-ttu-id="51e52-153">TestDropPath</span><span class="sxs-lookup"><span data-stu-id="51e52-153">TestDropPath</span></span>|<span data-ttu-id="51e52-154">String</span><span class="sxs-lookup"><span data-stu-id="51e52-154">String</span></span>|<span data-ttu-id="51e52-155">이 속성이 설정 되 면 모든 전자 메일이 지정 된 파일에도 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-155">When this property is set, all emails are also saved in the specified file.</span></span><br /><br /> <span data-ttu-id="51e52-156">이 속성은 워크플로를 테스트 하거나 디버그할 때 발신 전자 메일의 형식과 콘텐츠가 적절 한지 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-156">This property is intended to be used when you are testing or debugging workflows, to make sure that the format and contents of the outgoing emails is appropriate.</span></span>|  
  
## <a name="solution-contents"></a><span data-ttu-id="51e52-157">솔루션 개념</span><span class="sxs-lookup"><span data-stu-id="51e52-157">Solution Contents</span></span>  

 <span data-ttu-id="51e52-158">솔루션에는 두 개의 프로젝트가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-158">The solution contains two projects.</span></span>  
  
|<span data-ttu-id="51e52-159">프로젝트</span><span class="sxs-lookup"><span data-stu-id="51e52-159">Project</span></span>|<span data-ttu-id="51e52-160">설명</span><span class="sxs-lookup"><span data-stu-id="51e52-160">Description</span></span>|<span data-ttu-id="51e52-161">중요한 파일</span><span class="sxs-lookup"><span data-stu-id="51e52-161">Important Files</span></span>|  
|-------------|-----------------|---------------------|  
|<span data-ttu-id="51e52-162">SendMail</span><span class="sxs-lookup"><span data-stu-id="51e52-162">SendMail</span></span>|<span data-ttu-id="51e52-163">SendMail 활동</span><span class="sxs-lookup"><span data-stu-id="51e52-163">The SendMail activity</span></span>|<span data-ttu-id="51e52-164">1. SendMail.cs: 기본 작업에 대 한 구현</span><span class="sxs-lookup"><span data-stu-id="51e52-164">1.  SendMail.cs: implementation for the main activity</span></span><br /><span data-ttu-id="51e52-165">2. SendMailDesigner .xaml 및 SendMailDesigner.xaml.cs: SendMail 활동을 위한 디자이너</span><span class="sxs-lookup"><span data-stu-id="51e52-165">2.  SendMailDesigner.xaml and SendMailDesigner.xaml.cs: designer for the SendMail activity</span></span><br /><span data-ttu-id="51e52-166">3. MailTemplateBody.htm: 보낼 전자 메일의 템플릿입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-166">3.  MailTemplateBody.htm: template for the email to be sent out.</span></span>|  
|<span data-ttu-id="51e52-167">SendMailTestClient</span><span class="sxs-lookup"><span data-stu-id="51e52-167">SendMailTestClient</span></span>|<span data-ttu-id="51e52-168">SendMail 활동을 테스트할 클라이언트입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-168">Client to test the SendMail activity.</span></span>  <span data-ttu-id="51e52-169">이 프로젝트에서는 SendMail 활동을 호출하는 두 가지 방식, 즉 선언 방식과 프로그래밍 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-169">This project demonstrates two ways of invoking the SendMail activity: declaratively, and programmatically.</span></span>|<span data-ttu-id="51e52-170">sequence1.xaml: SendMail 활동을 호출 하는 워크플로입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-170">1.  Sequence1.xaml: workflow that invokes the SendMail activity.</span></span><br /><span data-ttu-id="51e52-171">Program.cs: Sequence1.xaml를 호출 하 고 SendMail을 사용 하는 워크플로를 프로그래밍 방식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-171">2.  Program.cs: invokes Sequence1 and also creates a workflow programmatically that uses SendMail.</span></span>|  
  
## <a name="further-configuration-of-the-sendmail-activity"></a><span data-ttu-id="51e52-172">SendMail 활동의 추가 구성</span><span class="sxs-lookup"><span data-stu-id="51e52-172">Further configuration of the SendMail activity</span></span>  

 <span data-ttu-id="51e52-173">샘플에는 표시되지 않지만 사용자는 SendMail 활동의 구성을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-173">Although not shown in the sample, users can perform addition configuration of the SendMail activity.</span></span> <span data-ttu-id="51e52-174">다음 세 개의 섹션에서는 이를 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-174">The next three sections demonstrate how this is done.</span></span>  
  
### <a name="sending-an-email-using-tokens-specified-in-the-body"></a><span data-ttu-id="51e52-175">본문에 지정된 토큰을 사용하여 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="51e52-175">Sending an email using tokens specified in the body</span></span>  

 <span data-ttu-id="51e52-176">이 코드 조각에서는 본문에 토큰이 포함된 전자 메일을 보낼 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-176">This code snippet demonstrates how you can send email with tokens in the body.</span></span> <span data-ttu-id="51e52-177">토큰이 본문 속성에 어떻게 제공되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-177">Notice how the tokens are provided in the body property.</span></span> <span data-ttu-id="51e52-178">해당 토큰 값은 토큰 속성에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-178">Values for those tokens are provided to the tokens property.</span></span>  
  
```csharp  
IDictionary<string, string> tokens = new Dictionary<string, string>();  
tokens.Add("@name", "John Doe");  
tokens.Add("@date", DateTime.Now.ToString());  
tokens.Add("@server", "localhost");  
  
new SendMail  
{  
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Body = "Hello @name. This is a test email sent from @server. Current date is @date",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens)  
};  
```  
  
### <a name="sending-an-email-using-a-template"></a><span data-ttu-id="51e52-179">템플릿을 사용하여 전자 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="51e52-179">Sending an email using a template</span></span>  

 <span data-ttu-id="51e52-180">이 조각에서는 본문의 템플릿 토큰을 사용하여 전자 메일을 보내는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-180">This snippet shows how to send an email using a template tokens in the body.</span></span> <span data-ttu-id="51e52-181">`BodyTemplateFilePath` 속성을 설정할 때 Body 속성 값을 제공할 필요가 없습니다. 템플릿 파일의 내용이 본문에 복사되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-181">Notice that when setting the `BodyTemplateFilePath` property we don’t need to provide the value for Body property (the contents of the template file will be copied to the body).</span></span>  
  
```csharp  
new SendMail  
{
    From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
    To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
    Subject = "Test email",  
    Host = "localhost",  
    Port = 25,  
    Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
    BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",
};  
```  
  
### <a name="sending-mails-in-testing-mode"></a><span data-ttu-id="51e52-182">테스트 모드에서 메일 보내기</span><span class="sxs-lookup"><span data-stu-id="51e52-182">Sending Mails in Testing Mode</span></span>  

 <span data-ttu-id="51e52-183">이 코드 조각에서는 두 개의 테스트 속성을 설정 하는 방법을 보여 줍니다 .를로 설정 하면 `TestMailTo` 모든 메시지를로 보냅니다 `john.doe@contoso.con` .</span><span class="sxs-lookup"><span data-stu-id="51e52-183">This code snippet shows how to set the two testing properties: by setting `TestMailTo` to all messages will be sent to `john.doe@contoso.con` (without regard of the values of To, Cc, Bcc).</span></span> <span data-ttu-id="51e52-184">TestDropPath를 설정하면 나가는 모든 전자 메일이 제공된 경로에도 기록됩니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-184">By setting TestDropPath all outgoing emails will be also recorded in the provided path.</span></span> <span data-ttu-id="51e52-185">이러한 속성은 서로 관련되어 있지 않으므로 독립적으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-185">These properties can be set independently (they are not related).</span></span>  
  
```csharp  
new SendMail  
{
   From = new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   To = new LambdaValue<MailAddressCollection>(  
                    ctx => new MailAddressCollection() { new MailAddress("someone@microsoft.com") }),  
   Subject = "Test email",  
   Host = "localhost",  
   Port = 25,  
   Tokens = new LambdaValue<IDictionary<string, string>>(ctx => tokens),  
   BodyTemplateFilePath = @"..\..\..\SendMail\Templates\MailTemplateBody.htm",  
   TestMailTo= new LambdaValue<MailAddress>(ctx => new MailAddress("john.doe@contoso.com")),  
   TestDropPath = @"c:\Samples\SendMail\TestDropPath\",  
};  
```  
  
## <a name="set-up-instructions"></a><span data-ttu-id="51e52-186">설치 지침</span><span class="sxs-lookup"><span data-stu-id="51e52-186">Set-Up Instructions</span></span>  

 <span data-ttu-id="51e52-187">이 샘플을 실행하려면 SMTP 서버에 액세스해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-187">Access to a SMTP server is required for this sample.</span></span>  
  
 <span data-ttu-id="51e52-188">SMTP 서버를 설정 하는 방법에 대 한 자세한 내용은 다음 링크를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="51e52-188">For more information about setting up a SMTP server, see the following links.</span></span>  
  
- <span data-ttu-id="51e52-189">[Configuring the SMTP Service (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="51e52-189">[Configuring the SMTP Service (IIS 6.0)](/previous-versions/windows/it-pro/windows-server-2003/cc784968(v=ws.10))</span></span>  
  
- <span data-ttu-id="51e52-190">[IIS 7.0: SMTP 전자 메일 구성](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="51e52-190">[IIS 7.0: Configure SMTP E-Mail](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc772058(v=ws.10))</span></span>  
  
- <span data-ttu-id="51e52-191">[SMTP 서비스를 설치하는 방법](/previous-versions/tn-archive/aa997480(v=exchg.65))</span><span class="sxs-lookup"><span data-stu-id="51e52-191">[How to Install the SMTP Service](/previous-versions/tn-archive/aa997480(v=exchg.65))</span></span>  
  
 <span data-ttu-id="51e52-192">타사에서 제공하는 SMTP 에뮬레이터를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-192">SMTP emulators provided by third parties are available for download.</span></span>  
  
##### <a name="to-run-this-sample"></a><span data-ttu-id="51e52-193">이 샘플을 실행하려면</span><span class="sxs-lookup"><span data-stu-id="51e52-193">To run this sample</span></span>  
  
1. <span data-ttu-id="51e52-194">Visual Studio 2010을 사용 하 여 SendMail 솔루션 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-194">Using Visual Studio 2010, open the SendMail.sln solution file.</span></span>  
  
2. <span data-ttu-id="51e52-195">올바른 SMTP 서버에 액세스할 수 있는 권한이 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-195">Ensure that you have access to a valid SMTP server.</span></span> <span data-ttu-id="51e52-196">설치 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="51e52-196">See the set-up instructions.</span></span>  
  
3. <span data-ttu-id="51e52-197">서버 주소를 사용 하 여 프로그램을 구성 하 고 및에서 전자 메일 주소로 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-197">Configure the program with your server address, and From and To email addresses.</span></span>  
  
     <span data-ttu-id="51e52-198">이 샘플을 올바르게 실행 하려면 Program.cs 및 .xaml에서 전자 메일 주소와 SMTP 서버의 주소에서 값을 구성 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-198">To correctly run this sample, you may need to configure the value of From and To email addresses and the address of the SMTP server in  Program.cs and in Sequence.xaml.</span></span> <span data-ttu-id="51e52-199">프로그램은 메일을 두 가지 다른 방식으로 보내므로 두 위치에서 모두 주소를 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-199">You will need to change the address in both locations since the program sends mail in two different ways</span></span>  
  
4. <span data-ttu-id="51e52-200">Ctrl+Shift+B를 눌러 솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-200">To build the solution, press CTRL+SHIFT+B.</span></span>  
  
5. <span data-ttu-id="51e52-201">Ctrl+F5를 눌러 솔루션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-201">To run the solution, press CTRL+F5.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="51e52-202">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-202">The samples may already be installed on your machine.</span></span> <span data-ttu-id="51e52-203">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="51e52-203">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="51e52-204">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-204">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="51e52-205">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51e52-205">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WF\Scenario\ActivityLibrary\SendMail`
