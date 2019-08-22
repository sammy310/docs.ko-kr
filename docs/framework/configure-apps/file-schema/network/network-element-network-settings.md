---
title: <network> 요소(네트워크 설정)
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#network
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.net/mailSettings/smtp/network
helpviewer_keywords:
- <network> element
- network element
ms.assetid: 2c2c6ad4-ed11-48ab-b28e-2bc0ba9b42c7
ms.openlocfilehash: 40d89f7bd7a1f4a38a1c4030a86405e09c497899
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/21/2019
ms.locfileid: "69659309"
---
# <a name="network-element-network-settings"></a><span data-ttu-id="4a871-102">\<network > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4a871-102">\<network> Element (Network Settings)</span></span>
<span data-ttu-id="4a871-103">외부 SMTP (Simple Mail Transport Protocol) 서버에 대 한 네트워크 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-103">Configures the network options for an external Simple Mail Transport Protocol (SMTP) server.</span></span>  
  
 <span data-ttu-id="4a871-104">\<configuration></span><span class="sxs-lookup"><span data-stu-id="4a871-104">\<configuration></span></span>  
<span data-ttu-id="4a871-105">\<system.net></span><span class="sxs-lookup"><span data-stu-id="4a871-105">\<system.net></span></span>  
<span data-ttu-id="4a871-106">\<mailSettings></span><span class="sxs-lookup"><span data-stu-id="4a871-106">\<mailSettings></span></span>  
<span data-ttu-id="4a871-107">\<smtp></span><span class="sxs-lookup"><span data-stu-id="4a871-107">\<smtp></span></span>  
<span data-ttu-id="4a871-108">\<network></span><span class="sxs-lookup"><span data-stu-id="4a871-108">\<network></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a871-109">구문</span><span class="sxs-lookup"><span data-stu-id="4a871-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="4a871-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="4a871-110">Attributes and Elements</span></span>  
 <span data-ttu-id="4a871-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="4a871-112">특성</span><span class="sxs-lookup"><span data-stu-id="4a871-112">Attributes</span></span>  
  
|<span data-ttu-id="4a871-113">특성</span><span class="sxs-lookup"><span data-stu-id="4a871-113">Attribute</span></span>|<span data-ttu-id="4a871-114">Description</span><span class="sxs-lookup"><span data-stu-id="4a871-114">Description</span></span>|  
|---------------|-----------------|  
|`clientDomain`|<span data-ttu-id="4a871-115">SMTP 메일 서버에 연결 하기 위해 초기 SMTP 프로토콜 요청에 사용할 클라이언트 도메인 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-115">Specifies the client domain name to use in the initial SMTP protocol request to connect to the SMTP mail server.</span></span> <span data-ttu-id="4a871-116">기본값은 요청을 보내는 로컬 컴퓨터의 localhost 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-116">The default value is the localhost name of the local computer sending the request.</span></span>|  
|`defaultCredentials`|<span data-ttu-id="4a871-117">Smtp 트랜잭션을 위해 SMTP 메일 서버에 액세스 하는 데 기본 사용자 자격 증명을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-117">Specifies whether the default user credentials should be used to access the SMTP mail server for SMTP transactions.</span></span> <span data-ttu-id="4a871-118">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-118">The default value is `false`.</span></span>|  
|`enableSsl`|<span data-ttu-id="4a871-119">SMTP 메일 서버에 액세스 하는 데 SSL을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-119">Specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="4a871-120">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-120">The default value is `false`.</span></span>|  
|`host`|<span data-ttu-id="4a871-121">SMTP 트랜잭션에 사용할 SMTP 메일 서버의 호스트 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-121">Specifies the hostname of the SMTP mail server to use for SMTP transactions.</span></span> <span data-ttu-id="4a871-122">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-122">This attribute has no default value.</span></span>|  
|`password`|<span data-ttu-id="4a871-123">SMTP 메일 서버에 대 한 인증에 사용할 암호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-123">Specifies the password to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="4a871-124">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-124">This attribute has no default value.</span></span>|  
|`port`|<span data-ttu-id="4a871-125">SMTP 메일 서버에 연결 하는 데 사용할 포트 번호를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-125">Specifies the port number to use to connect to the SMTP mail server.</span></span> <span data-ttu-id="4a871-126">기본값은 25입니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-126">The default value is 25.</span></span>|  
|`targetName`|<span data-ttu-id="4a871-127">SMTP 트랜잭션에 대해 확장 된 보호를 사용 하는 경우 인증에 사용할 SPN (서비스 공급자 이름)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-127">Specifies the Service Provider Name (SPN) to use for authentication when using extended protection for SMTP transactions.</span></span> <span data-ttu-id="4a871-128">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-128">This attribute has no default value.</span></span>|  
|`userName`|<span data-ttu-id="4a871-129">SMTP 메일 서버에 대 한 인증에 사용할 사용자 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-129">Specifies the user name to use for authentication to the SMTP mail server.</span></span> <span data-ttu-id="4a871-130">이 특성에는 기본값이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-130">This attribute has no default value.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="4a871-131">자식 요소</span><span class="sxs-lookup"><span data-stu-id="4a871-131">Child Elements</span></span>  
 <span data-ttu-id="4a871-132">없음</span><span class="sxs-lookup"><span data-stu-id="4a871-132">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="4a871-133">부모 요소</span><span class="sxs-lookup"><span data-stu-id="4a871-133">Parent Elements</span></span>  
  
|<span data-ttu-id="4a871-134">요소</span><span class="sxs-lookup"><span data-stu-id="4a871-134">Element</span></span>|<span data-ttu-id="4a871-135">설명</span><span class="sxs-lookup"><span data-stu-id="4a871-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="4a871-136">\<smtp > 요소 (네트워크 설정)</span><span class="sxs-lookup"><span data-stu-id="4a871-136">\<smtp> Element (Network Settings)</span></span>](smtp-element-network-settings.md)|<span data-ttu-id="4a871-137">SMTP (Simple Mail Transport Protocol) 메일 전송 옵션을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-137">Configures Simple Mail Transport Protocol (SMTP) mail sending options.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4a871-138">설명</span><span class="sxs-lookup"><span data-stu-id="4a871-138">Remarks</span></span>  
 <span data-ttu-id="4a871-139">일부 SMTP 서버에서는를 사용 하기 전에 서버에 대해 사용자를 인증 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-139">Some SMTP servers require that you authenticate yourself to the server before use.</span></span> <span data-ttu-id="4a871-140">호스트에서 기본 네트워크 자격 증명을 사용 하 여 자신을 인증 하려면 `defaultCredentials` 특성을로 `true`설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-140">If you want to authenticate yourself using the default network credentials on your host, set the `defaultCredentials` attribute to `true`.</span></span> <span data-ttu-id="4a871-141">속성을 사용 하 여 적용 가능한 구성 파일에서 `defaultCredentials` 특성의 현재 값을 가져올 수 있습니다. <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4a871-141">The <xref:System.Net.Configuration.SmtpNetworkElement.DefaultCredentials%2A?displayProperty=nameWithType> property can be used to get the current value of the `defaultCredentials` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="4a871-142">기본 인증 (사용자 이름 및 암호)을 사용 하 여 SMTP 서버에 대해 자신을 인증할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-142">You can also use basic authentication (a user name and password) to authenticate yourself to the SMTP server.</span></span> <span data-ttu-id="4a871-143">이 옵션을 사용 하려면 지정 된 SMTP 서버에 대 한 유효한 사용자 이름 및 암호를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-143">To use this option, you must specify a valid user name and password for the specified SMTP server.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4a871-144">기본 인증에서는 `userName` 암호화 되지 `password` 않은 서버에 및 값을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-144">Basic authentication sends the `userName` and `password` values to the server unencrypted.</span></span> <span data-ttu-id="4a871-145">네트워크 트래픽을 모니터링 하는 모든 자격 증명을 확인 하 고 하는 서버에 연결 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-145">Anyone monitoring network traffic can view your credentials and use them to connect to the server.</span></span> <span data-ttu-id="4a871-146">Kerberos 또는 NT LAN Manager (NTLM)와 같은 보다 안전한 인증 메커니즘을 사용 하는 것을 고려해 야 합니다. `defaultCredentials` 가`true`이면 서버에서 이러한 프로토콜을 지 원하는 경우 Kerberos 또는 NTLM이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-146">You should consider using a more secure authentication mechanism, such as Kerberos or NT LAN Manager (NTLM.) If `defaultCredentials` is `true`, Kerberos or NTLM will be used if the server supports these protocols.</span></span>  
  
 <span data-ttu-id="4a871-147">기본 인증 및 기본 네트워크 자격 증명 옵션은 함께 사용할 수 없습니다. 을로 `defaultCredentials` `true` 설정 하 고 사용자 이름과 암호를 지정 하면 기본 네트워크 자격 증명이 사용 되 고 기본 인증 데이터는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-147">The basic authentication and default network credentials options are mutually exclusive; if you set `defaultCredentials` to `true` and specify a user name and password, the default network credential is used, and the basic authentication data is ignored.</span></span>  
  
 <span data-ttu-id="4a871-148">기본 인증의 경우를 지정 `userName`하는 경우 메일 서버에 직접 인증 하는 `password` 도 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-148">For basic authentication if you specify a `userName`, you should also specify a `password` to authentication yourself to the mail server.</span></span>  
  
 <span data-ttu-id="4a871-149">속성을 사용 하 여 적용 가능한 구성 파일에서 `userName` 특성의 현재 값을 가져올 수 있습니다. <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4a871-149">The <xref:System.Net.Configuration.SmtpNetworkElement.UserName%2A?displayProperty=nameWithType> property can be used to get the current value of the `userName` attribute from applicable configuration files.</span></span> <span data-ttu-id="4a871-150">속성을 사용 하 여 적용 가능한 구성 파일에서 `password` 특성의 현재 값을 가져올 수 있습니다. <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4a871-150">The <xref:System.Net.Configuration.SmtpNetworkElement.Password%2A?displayProperty=nameWithType> property can be used to get the current value of the `password` attribute from applicable configuration files.</span></span> <span data-ttu-id="4a871-151">특성 `password` 은 일반적으로 보안상의 이유로 구성 파일에 입력 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-151">A `password` attribute would not normally be entered in configuration files for security reasons.</span></span>  
  
 <span data-ttu-id="4a871-152">특성 `clientDomain` 은 초기 smtp 프로토콜 요청에 사용 된 클라이언트 도메인 이름을 smtp 서버로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-152">The `clientDomain` attribute changes the client domain name used in the initial SMTP protocol request to an SMTP server.</span></span> <span data-ttu-id="4a871-153">특성 `clientDomain` 은 기본적으로 사용 되는 localhost 이름이 아니라 로컬 컴퓨터의 정규화 된 도메인 이름으로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-153">The `clientDomain` attribute can be set to the fully-qualified domain name of the local machine, rather than the localhost name that is used by default.</span></span> <span data-ttu-id="4a871-154">이 큰 SMTP 프로토콜 표준 준수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-154">This provides greater compliance with the SMTP protocol standards.</span></span> <span data-ttu-id="4a871-155">기본값은 요청을 보내는 로컬 컴퓨터의 localhost 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-155">The default value is the localhost name of the local computer sending the request.</span></span> <span data-ttu-id="4a871-156">속성을 사용 하 여 적용 가능한 구성 파일에서 `clientDomain` 특성의 현재 값을 가져올 수 있습니다. <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4a871-156">The <xref:System.Net.Configuration.SmtpNetworkElement.ClientDomain%2A?displayProperty=nameWithType> property can be used to get the current value of the `clientDomain` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="4a871-157">특성 `targetName` 은 확장 된 보호를 사용 하는 경우 인증에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-157">The `targetName` attribute is used for authentication when using extended protection.</span></span> <span data-ttu-id="4a871-158">기본값은 "SMTPSVC/\<host >" 형식입니다. 여기서 \<host >는 SMTP 메일 서버의 호스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-158">The default value is of the form "SMTPSVC/\<host>" where \<host> is the hostname of the SMTP mail server.</span></span> <span data-ttu-id="4a871-159">속성을 사용 하 여 적용 가능한 구성 파일에서 `targetName` 특성의 현재 값을 가져올 수 있습니다. <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4a871-159">The <xref:System.Net.Configuration.SmtpNetworkElement.TargetName%2A?displayProperty=nameWithType> property can be used to get the current value of the `targetName` attribute from applicable configuration files.</span></span>  
  
 <span data-ttu-id="4a871-160">특성 `enableSsl` 은 SMTP 메일 서버에 액세스 하는 데 SSL을 사용할지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-160">The `enableSsl` attribute specifies whether SSL is used to access an SMTP mail server.</span></span> <span data-ttu-id="4a871-161"><xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> 클래스 SMTP 서비스 확장에 대해만 지원 SMTP 보안 전송 계층 보안을 통해 3207 RFC에에서 정의 된 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-161">The <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType> class only supports the SMTP Service Extension for Secure SMTP over Transport Layer Security as defined in RFC 3207.</span></span> <span data-ttu-id="4a871-162">이 모드에서는 SMTP 세션이 시작 된 암호화 되지 않은 채널에 다음 STARTTLS 명령을 실행 하는 SSL을 사용 하 여 보안 통신을 전환 하려면 서버에 클라이언트에서 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-162">In this mode, the SMTP session begins on an unencrypted channel, then a STARTTLS command is issued by the client to the server to switch to secure communication using SSL.</span></span> <span data-ttu-id="4a871-163">RFC 3207 게시 하 여는 Task Force IETF (Internet Engineering)에 대 한 자세한 내용은 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4a871-163">See RFC 3207 published by the Internet Engineering Task Force (IETF) for more information.</span></span>  
  
 <span data-ttu-id="4a871-164">대체 연결 메서드 명령을 보내는 모든 프로토콜 하기 전에 SSL 세션을 선불 하 게 설정 하는 경우</span><span class="sxs-lookup"><span data-stu-id="4a871-164">An alternate connection method is where an SSL session is established up front before any protocol commands are sent.</span></span> <span data-ttu-id="4a871-165">이 연결 방법을 SMTPS 라고 하 고 기본적으로 포트 465를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-165">This connection method is sometimes called SMTPS and by default uses port 465.</span></span> <span data-ttu-id="4a871-166">이 대체 연결 방법은 SSL을 사용 하 여 현재 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-166">This alternate connection method using SSL is not currently supported.</span></span>  
  
 <span data-ttu-id="4a871-167">속성을 사용 하 여 적용 가능한 구성 파일에서 `enableSsl` 특성의 현재 값을 가져올 수 있습니다. <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType></span><span class="sxs-lookup"><span data-stu-id="4a871-167">The <xref:System.Net.Configuration.SmtpNetworkElement.EnableSsl%2A?displayProperty=nameWithType> property can be used to get the current value of the `enableSsl` attribute from applicable configuration files.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4a871-168">예제</span><span class="sxs-lookup"><span data-stu-id="4a871-168">Example</span></span>  
 <span data-ttu-id="4a871-169">다음 예에서는 기본 네트워크 자격 증명을 사용 하 여 전자 메일을 보낼 적절 한 SMTP 매개 변수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a871-169">The following example specifies the appropriate SMTP parameters to send email using the default network credentials.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="4a871-170">참고자료</span><span class="sxs-lookup"><span data-stu-id="4a871-170">See also</span></span>

- <xref:System.Net.Configuration.SmtpNetworkElement?displayProperty=nameWithType>
- <xref:System.Net.Configuration.SmtpSection?displayProperty=nameWithType>
- <xref:System.Net.Mail.SmtpClient?displayProperty=nameWithType>
- [<span data-ttu-id="4a871-171">네트워크 설정 스키마</span><span class="sxs-lookup"><span data-stu-id="4a871-171">Network Settings Schema</span></span>](index.md)
