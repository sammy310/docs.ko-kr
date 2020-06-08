---
title: <network> 요소(네트워크 설정)
description: <network>네트워크 설정 요소는 .NET Framework에서 외부 SMTP 서버 옵션의 네트워크 옵션을 구성 합니다.
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 36857e63871b4672df349934594f0887a042609e
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504552"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="36d2e-103">\<network> 요소(네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="36d2e-103">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="36d2e-104">외부 SMTP (Simple Mail Transport Protocol) 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-104">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  

[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.net>**](system-net-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<mailSettings>**](mailsettings-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<smtp>**](smtp-element-network-settings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<network>**

## <a name="syntax"></a><span data-ttu-id="36d2e-105">구문</span><span class="sxs-lookup"><span data-stu-id="36d2e-105">Syntax</span></span>  
  
```xml  
<network  
  clientDomain="string"
  defaultCredentials="true|false"  
  enableSsl="true|false"  
  host="string"
  password="string"  
  port="integer"
  targetName="string"  
  userName="string"  
/>  
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36d2e-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36d2e-106">Attributes and Elements</span></span>  
 <span data-ttu-id="36d2e-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36d2e-108">특성</span><span class="sxs-lookup"><span data-stu-id="36d2e-108">Attributes</span></span>  
  
|<span data-ttu-id="36d2e-109">특성</span><span class="sxs-lookup"><span data-stu-id="36d2e-109">Attribute</span></span>|<span data-ttu-id="36d2e-110">설명</span><span class="sxs-lookup"><span data-stu-id="36d2e-110">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="36d2e-111">SMTP 메일 서버에 연결 하기 위해 초기 SMTP 프로토콜 요청에 사용할 클라이언트 도메인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-111">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="36d2e-112">기본값은 요청을 보내는 로컬 컴퓨터의 localhost 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-112">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="36d2e-113">Smtp 트랜잭션을 위해 SMTP 메일 서버에 액세스 하는 데 기본 사용자 자격 증명을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-113">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="36d2e-114">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-114">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="36d2e-115">SMTP 메일 서버에 액세스 하는 데 SSL을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-115">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="36d2e-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-116">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="36d2e-117">SMTP 트랜잭션에 사용할 SMTP 메일 서버의 호스트 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-117">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="36d2e-118">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-118">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="36d2e-119">SMTP 메일 서버에 대 한 인증에 사용할 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-119">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="36d2e-120">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-120">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="36d2e-121">SMTP 메일 서버에 연결 하는 데 사용할 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-121">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="36d2e-122">기본값은 25입니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-122">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="36d2e-123">SMTP 트랜잭션에 대해 확장 된 보호를 사용 하는 경우 인증에 사용할 SPN (서비스 공급자 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-123">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="36d2e-124">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-124">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="36d2e-125">SMTP 메일 서버에 대 한 인증에 사용할 사용자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-125">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="36d2e-126">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-126">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36d2e-127">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36d2e-127">Child Elements</span></span>  
 <span data-ttu-id="36d2e-128">없음</span><span class="sxs-lookup"><span data-stu-id="36d2e-128">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36d2e-129">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36d2e-129">Parent Elements</span></span>  
  
|<span data-ttu-id="36d2e-130">요소</span><span class="sxs-lookup"><span data-stu-id="36d2e-130">Element</span></span>|<span data-ttu-id="36d2e-131">설명</span><span class="sxs-lookup"><span data-stu-id="36d2e-131">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36d2e-132">\<smtp>요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="36d2e-132">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="36d2e-133">SMTP (Simple Mail Transport Protocol) 메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-133">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="36d2e-134">설명</span><span class="sxs-lookup"><span data-stu-id="36d2e-134">Remarks</span></span>  
 <span data-ttu-id="36d2e-135">일부 SMTP 서버에서는를 사용 하기 전에 서버에 대해 사용자를 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-135">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="36d2e-136">호스트에서 기본 네트워크 자격 증명을 사용 하 여 자신을 인증 하려면 `defaultCredentials` 특성을로 설정 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-136">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="36d2e-137"><xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType>속성을 사용 하 여 `defaultCredentials` 적용 가능한 구성 파일에서 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-137">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="36d2e-138">기본 인증 (사용자 이름 및 암호)을 사용 하 여 SMTP 서버에 대해 자신을 인증할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-138">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="36d2e-139">이 옵션을 사용 하려면 지정 된 SMTP 서버에 대 한 유효한 사용자 이름 및 암호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-139">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="36d2e-140">기본 인증에서는 `userName` `password` 암호화 되지 않은 서버에 및 값을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-140">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="36d2e-141">네트워크 트래픽을 모니터링 하는 사람은 누구나 자격 증명을 확인 하 고이를 사용 하 여 서버에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-141">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="36d2e-142">Kerberos 또는 NT LAN Manager (NTLM)와 같은 보다 안전한 인증 메커니즘을 사용 하는 것을 고려해 야 합니다. `defaultCredentials`가 이면 `true` 서버에서 이러한 프로토콜을 지 원하는 경우 KERBEROS 또는 NTLM이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-142">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="36d2e-143">기본 인증 및 기본 네트워크 자격 증명 옵션은 함께 사용할 수 없습니다. `defaultCredentials`을로 설정 하 `true` 고 사용자 이름과 암호를 지정 하면 기본 네트워크 자격 증명이 사용 되 고 기본 인증 데이터는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-143">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="36d2e-144">기본 인증의 경우를 지정 하는 경우 `userName` `password` 메일 서버에 직접 인증 하는도 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-144">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="36d2e-145"><xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType>속성을 사용 하 여 `userName` 적용 가능한 구성 파일에서 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-145">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="36d2e-146"><xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType>속성을 사용 하 여 `password` 적용 가능한 구성 파일에서 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-146">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="36d2e-147">`password`특성은 일반적으로 보안상의 이유로 구성 파일에 입력 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-147">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="36d2e-148">`clientDomain`특성은 초기 smtp 프로토콜 요청에 사용 된 클라이언트 도메인 이름을 smtp 서버로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-148">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="36d2e-149">`clientDomain`특성은 기본적으로 사용 되는 localhost 이름이 아니라 로컬 컴퓨터의 정규화 된 도메인 이름으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-149">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="36d2e-150">이 큰 SMTP 프로토콜 표준 준수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-150">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="36d2e-151">기본값은 요청을 보내는 로컬 컴퓨터의 localhost 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-151">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="36d2e-152"><xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType>속성을 사용 하 여 `clientDomain` 적용 가능한 구성 파일에서 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-152">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="36d2e-153">`targetName`특성은 확장 된 보호를 사용 하는 경우 인증에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-153">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="36d2e-154">기본값은 "SMTPSVC/" 형식입니다 \<host> \<host> . 여기서는 SMTP 메일 서버의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-154">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="36d2e-155"><xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType>속성을 사용 하 여 `targetName` 적용 가능한 구성 파일에서 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-155">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="36d2e-156">`enableSsl`특성은 SMTP 메일 서버에 액세스 하는 데 SSL을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-156">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="36d2e-157"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> 클래스 SMTP 서비스 확장에 대해만 지원 SMTP 보안 전송 계층 보안을 통해 3207 RFC에에서 정의 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-157">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="36d2e-158">이 모드에서는 SMTP 세션이 시작 된 암호화 되지 않은 채널에 다음 STARTTLS 명령을 실행 하는 SSL을 사용 하 여 보안 통신을 전환 하려면 서버에 클라이언트에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-158">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="36d2e-159">RFC 3207 게시 하 여는 Task Force IETF (Internet Engineering)에 대 한 자세한 내용은 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="36d2e-159">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="36d2e-160">대체 연결 메서드 명령을 보내는 모든 프로토콜 하기 전에 SSL 세션을 선불 하 게 설정 하는 경우</span><span class="sxs-lookup"><span data-stu-id="36d2e-160">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="36d2e-161">이 연결 방법을 SMTPS 라고 하 고 기본적으로 포트 465를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-161">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="36d2e-162">이 대체 연결 방법은 SSL을 사용 하 여 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-162">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="36d2e-163"><xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType>속성을 사용 하 여 `enableSsl` 적용 가능한 구성 파일에서 특성의 현재 값을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-163">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="36d2e-164">예제</span><span class="sxs-lookup"><span data-stu-id="36d2e-164">Example</span></span>  
 <span data-ttu-id="36d2e-165">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="36d2e-165">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
```xml  
<configuration>  
  <system.net>  
    <mailSettings>  
      <smtp deliveryMethod="Network">  
        <network  
          clientDomain="www.contoso.com"  
          defaultCredentials="true"  
          enableSsl="false"  
          host="mail.contoso.com"  
          port="25"  
        />  
      </smtp>  
    </mailSettings>  
  </system.net>  
</configuration>  
```  
  
## <a name="see-also"></a><span data-ttu-id="36d2e-166">참고 항목</span><span class="sxs-lookup"><span data-stu-id="36d2e-166">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="36d2e-167">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="36d2e-167">Network Settings Schema</span></span>](index.md)
