---
title: '방법: 개발 중에 사용할 임시 인증서 만들기'
description: PowerShell cmdlet을 사용 하 여 보안 WCF 서비스 또는 클라이언트를 개발 하는 데 사용할 두 개의 임시 x.509 인증서를 만드는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], creating temporary certificates
- temporary certificates [WCF]
ms.assetid: bc5f6637-5513-4d27-99bb-51aad7741e4a
ms.openlocfilehash: 45df7b2c4dad1aa84ad39ca38fba8d2ec16c8fb3
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100585354"
---
# <a name="how-to-create-temporary-certificates-for-use-during-development"></a><span data-ttu-id="e158a-103">방법: 개발 중에 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="e158a-103">How to: Create Temporary Certificates for Use During Development</span></span>

<span data-ttu-id="e158a-104">WCF (Windows Communication Foundation)를 사용 하 여 보안 서비스 또는 클라이언트를 개발 하는 경우 자격 증명으로 사용할 x.509 인증서를 제공 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-104">When developing a secure service or client using Windows Communication Foundation (WCF), it is often necessary to supply an X.509 certificate to be used as a credential.</span></span> <span data-ttu-id="e158a-105">일반적으로 인증서는 루트 인증 기관이 컴퓨터의 신뢰할 수 있는 루트 인증 기관 저장소에 있는 인증서 체인의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-105">The certificate typically is part of a chain of certificates with a root authority found in the Trusted Root Certification Authorities store of the computer.</span></span> <span data-ttu-id="e158a-106">인증서 체인을 사용하면 일반적으로 루트 인증 기관이 조직 또는 비즈니스 사업부에 있는 인증서 집합의 범위를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-106">Having a certificate chain enables you to scope a set of certificates where typically the root authority is from your organization or business unit.</span></span> <span data-ttu-id="e158a-107">개발 시 이를 에뮬레이트하려면 보안 요구 사항에 맞는 두 개의 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-107">To emulate this at development time, you can create two certificates to satisfy the security requirements.</span></span> <span data-ttu-id="e158a-108">첫 번째 인증서는 신뢰할 수 있는 루트 인증 기관 저장소에 있는 자체 서명된 인증서이고, 두 번째 인증서는 첫 번째 인증서에서 만들어지고 로컬 컴퓨터 위치의 개인 저장소나 현재 사용자 위치의 개인 저장소에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-108">The first is a self-signed certificate that is placed in the Trusted Root Certification Authorities store, and the second certificate is created from the first and is placed in either the Personal store of the Local Machine location, or the Personal store of the Current User location.</span></span> <span data-ttu-id="e158a-109">이 항목에서는 PowerShell [new-selfsignedcertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet을 사용 하 여 이러한 두 인증서를 만드는 단계를 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-109">This topic walks through the steps to create these two certificates using the PowerShell [New-SelfSignedCertificate)](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e158a-110">New-SelfSignedCertificate cmdlet이 생성 하는 인증서는 테스트 목적 으로만 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-110">The certificates that the New-SelfSignedCertificate cmdlet generates are provided for testing purposes only.</span></span> <span data-ttu-id="e158a-111">서비스 또는 클라이언트를 배포할 때는 인증 기관에서 제공하는 적절한 인증서를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-111">When deploying a service or client, be sure to use an appropriate certificate provided by a certification authority.</span></span> <span data-ttu-id="e158a-112">이는 조직 또는 타사의 Windows Server 인증서 서버에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-112">This could either be from a Windows Server certificate server in your organization or a third party.</span></span>
>
> <span data-ttu-id="e158a-113">기본적으로 [new-selfsignedcertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet은 자체 서명 된 인증서를 만들며 이러한 인증서는 안전 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-113">By default, the [New-SelfSignedCertificate](/powershell/module/pkiclient/new-selfsignedcertificate) cmdlet creates certificates that are self-signed and these certificates are insecure.</span></span> <span data-ttu-id="e158a-114">자체 서명 된 인증서를 신뢰할 수 있는 루트 인증 기관 저장소에 배치 하면 배포 환경을 보다 긴밀 하 게 시뮬레이션 하는 개발 환경을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-114">Placing the self-signed certificates in the Trusted Root Certification Authorities store enables you to create a development environment that more closely simulates your deployment environment.</span></span>

 <span data-ttu-id="e158a-115">인증서를 만들고 사용 하는 방법에 대 한 자세한 내용은 [인증서 작업](working-with-certificates.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e158a-115">For more information about creating and using certificates, see [Working with Certificates](working-with-certificates.md).</span></span> <span data-ttu-id="e158a-116">인증서를 자격 증명으로 사용 하는 방법에 대 한 자세한 내용은 [서비스 및 클라이언트 보안](securing-services-and-clients.md)설정을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e158a-116">For more information about using a certificate as a credential, see [Securing Services and Clients](securing-services-and-clients.md).</span></span> <span data-ttu-id="e158a-117">Microsoft Authenticode 기술을 사용하는 방법에 대한 자습서는 [Authenticode Overviews and Tutorials](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85))를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e158a-117">For a tutorial about using Microsoft Authenticode technology, see [Authenticode Overviews and Tutorials](/previous-versions/windows/internet-explorer/ie-developer/platform-apis/ms537360(v=vs.85)).</span></span>

## <a name="to-create-a-self-signed-root-authority-certificate-and-export-the-private-key"></a><span data-ttu-id="e158a-118">자체 서명된 루트 인증 기관 인증서를 만들고 프라이빗 키를 내보내려면</span><span class="sxs-lookup"><span data-stu-id="e158a-118">To create a self-signed root authority certificate and export the private key</span></span>

<span data-ttu-id="e158a-119">다음 명령은 현재 사용자 개인 저장소에서 주체 이름이 "Rootca.cer" 인 자체 서명 된 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-119">The following command creates a self-signed certificate with a subject name of "RootCA" in the Current User Personal store.</span></span>

```powershell
$rootCert = New-SelfSignedCertificate -CertStoreLocation Cert:\CurrentUser\My -DnsName "RootCA" -TextExtension @("2.5.29.19={text}CA=true") -KeyUsage CertSign,CrlSign,DigitalSignature
```

<span data-ttu-id="e158a-120">이후 단계에서 필요한 곳으로 가져올 수 있도록 인증서를 PFX 파일로 내보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-120">We need to export the certificate to a PFX file so that it can be imported to where it's needed in a later step.</span></span> <span data-ttu-id="e158a-121">개인 키가 있는 인증서를 내보내는 경우 암호를 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-121">When exporting a certificate with the private key, a password is needed to protect it.</span></span> <span data-ttu-id="e158a-122">에서 암호를 저장 하 `SecureString` 고 [get-pfxcertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet을 사용 하 여 연결 된 개인 키가 포함 된 인증서를 PFX 파일로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-122">We save the password in a `SecureString` and use the [Export-PfxCertificate](/powershell/module/pkiclient/export-pfxcertificate) cmdlet to export the certificate with the associated private key to a PFX file.</span></span> <span data-ttu-id="e158a-123">또한 [내보내기 인증서](/powershell/module/pkiclient/export-certificate) cmdlet을 사용 하 여 공용 인증서만 CRT 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-123">We also save just the public certificate into a CRT file using the [Export-Certificate](/powershell/module/pkiclient/export-certificate) cmdlet.</span></span>

```powershell
[System.Security.SecureString]$rootCertPassword = ConvertTo-SecureString -String "password" -Force -AsPlainText
[String]$rootCertPath = Join-Path -Path 'cert:\CurrentUser\My\' -ChildPath "$($rootCert.Thumbprint)"
Export-PfxCertificate -Cert $rootCertPath -FilePath 'RootCA.pfx' -Password $rootCertPassword
Export-Certificate -Cert $rootCertPath -FilePath 'RootCA.crt'
```

## <a name="to-create-a-new-certificate-signed-by-a-root-authority-certificate"></a><span data-ttu-id="e158a-124">루트 인증 기관 인증서로 서명된 새 인증서를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e158a-124">To create a new certificate signed by a root authority certificate</span></span>

<span data-ttu-id="e158a-125">다음 명령은 `RootCA` 발급자의 개인 키를 사용 하 여 주체 이름이 "SignedByRootCA" 인로 서명 된 인증서를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-125">The following command creates a certificate signed by the `RootCA` with a subject name of "SignedByRootCA" using the private key of the issuer.</span></span>

```powershell
$testCert = New-SelfSignedCertificate -CertStoreLocation Cert:\LocalMachine\My -DnsName "SignedByRootCA" -KeyExportPolicy Exportable -KeyLength 2048 -KeyUsage DigitalSignature,KeyEncipherment -Signer $rootCert
```

<span data-ttu-id="e158a-126">마찬가지로 개인 키가 포함 된 서명 된 인증서를 PFX 파일로 저장 하 고, 공개 키만 CRT 파일에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-126">Similarly, we save the signed certificate with private key into a PFX file and just the public key into a CRT file.</span></span>

```powershell
[String]$testCertPath = Join-Path -Path 'cert:\LocalMachine\My\' -ChildPath "$($testCert.Thumbprint)"
Export-PfxCertificate -Cert $testCertPath -FilePath testcert.pfx -Password $rootCertPassword
Export-Certificate -Cert $testCertPath -FilePath testcert.crt
```

## <a name="installing-a-certificate-in-the-trusted-root-certification-authorities-store"></a><span data-ttu-id="e158a-127">신뢰할 수 있는 루트 인증 기관 저장소에 인증서 설치</span><span class="sxs-lookup"><span data-stu-id="e158a-127">Installing a Certificate in the Trusted Root Certification Authorities Store</span></span>

<span data-ttu-id="e158a-128">자체 서명된 인증서를 만들면 신뢰할 수 있는 루트 인증 기관 저장소에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-128">Once a self-signed certificate is created, you can install it in the Trusted Root Certification Authorities store.</span></span> <span data-ttu-id="e158a-129">이때 인증서로 서명된 모든 인증서는 컴퓨터에 의해 신뢰됩니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-129">Any certificates that are signed with the certificate at this point are trusted by the computer.</span></span> <span data-ttu-id="e158a-130">따라서 인증서가 더 이상 필요하지 않으면 즉시 저장소에서 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-130">For this reason, delete the certificate from the store as soon as you no longer need it.</span></span> <span data-ttu-id="e158a-131">이 루트 인증 기관 인증서를 삭제하면 해당 인증서로 서명된 다른 모든 인증서의 권한이 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-131">When you delete this root authority certificate, all other certificates that signed with it become unauthorized.</span></span> <span data-ttu-id="e158a-132">루트 인증 기관 인증서는 단순히 필요에 따라 인증서 그룹의 범위를 지정할 수 있는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-132">Root authority certificates are simply a mechanism whereby a group of certificates can be scoped as necessary.</span></span> <span data-ttu-id="e158a-133">예를 들어 피어 투 피어 애플리케이션에서는 일반적으로 제공된 인증서로 개인의 ID를 신뢰하므로 루트 인증 기관이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-133">For example, in peer-to-peer applications, there is typically no need for a root authority because you simply trust the identity of an individual by its supplied certificate.</span></span>

### <a name="to-install-a-self-signed-certificate-in-the-trusted-root-certification-authorities"></a><span data-ttu-id="e158a-134">신뢰할 수 있는 루트 인증 기관에 자체 서명된 인증서를 설치하려면</span><span class="sxs-lookup"><span data-stu-id="e158a-134">To install a self-signed certificate in the Trusted Root Certification Authorities</span></span>

1. <span data-ttu-id="e158a-135">인증서 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-135">Open the certificate snap-in.</span></span> <span data-ttu-id="e158a-136">자세한 내용은 [방법: MMC 스냅인을 사용하여 인증서 보기](how-to-view-certificates-with-the-mmc-snap-in.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e158a-136">For more information, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>

2. <span data-ttu-id="e158a-137">인증서를 저장할 폴더( **로컬 컴퓨터** 또는 **현재 사용자**)를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-137">Open the folder to store the certificate, either the **Local Computer** or the **Current User**.</span></span>

3. <span data-ttu-id="e158a-138">**신뢰할 수 있는 루트 인증 기관** 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-138">Open the **Trusted Root Certification Authorities** folder.</span></span>

4. <span data-ttu-id="e158a-139">**인증서** 폴더를 마우스 오른쪽 단추로 클릭하고 **모든 작업** 을 클릭한 다음 **가져오기** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-139">Right-click the **Certificates** folder and click **All Tasks**, then click **Import**.</span></span>

5. <span data-ttu-id="e158a-140">화면에 있는 마법사의 지침에 따라 Rootca.cer를 저장소로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-140">Follow the on-screen wizard instructions to import the RootCA.pfx into the store.</span></span>

## <a name="using-certificates-with-wcf"></a><span data-ttu-id="e158a-141">WCF에서 인증서 사용</span><span class="sxs-lookup"><span data-stu-id="e158a-141">Using certificates With WCF</span></span>

<span data-ttu-id="e158a-142">임시 인증서를 설정했으면 클라이언트 자격 증명 형식으로 인증서를 지정하는 WCF 솔루션을 이 인증서를 사용하여 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-142">Once you have set up the temporary certificates, you can use them to develop WCF solutions that specify certificates as a client credential type.</span></span> <span data-ttu-id="e158a-143">예를 들어 다음 XML 구성에서는 메시지 보안과 인증서를 클라이언트 자격 증명 형식으로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-143">For example, the following XML configuration specifies message security and a certificate as the client credential type.</span></span>

### <a name="to-specify-a-certificate-as-the-client-credential-type"></a><span data-ttu-id="e158a-144">인증서를 클라이언트 자격 증명 형식으로 지정하려면</span><span class="sxs-lookup"><span data-stu-id="e158a-144">To specify a certificate as the client credential type</span></span>

1. <span data-ttu-id="e158a-145">서비스의 구성 파일에서 다음 XML을 사용하여 보안 모드를 메시지로 설정하고 클라이언트 자격 증명 형식을 인증서로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-145">In the configuration file for a service, use the following XML to set the security mode to message, and the client credential type to certificate.</span></span>

    ```xml
    <bindings>
      <wsHttpBinding>
        <binding name="CertificateForClient">
          <security>
            <message clientCredentialType="Certificate" />
          </security>
        </binding>
      </wsHttpBinding>
    </bindings>
    ```

2. <span data-ttu-id="e158a-146">클라이언트의 구성 파일에서 다음 XML을 사용 하 여 인증서가 사용자 저장소에 있음을 지정 하 고 "CohoWinery" 값에 대 한 SubjectName 필드를 검색 하 여 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-146">In the configuration file for a client, use the following XML to specify that the certificate is found in the user’s store, and can be found by searching the SubjectName field for the value "CohoWinery."</span></span>

    ```xml
    <behaviors>
      <endpointBehaviors>
        <behavior name="CertForClient">
          <clientCredentials>
            <clientCertificate findValue="CohoWinery" x509FindType="FindBySubjectName" />
          </clientCredentials>
        </behavior>
      </endpointBehaviors>
    </behaviors>
    ```

<span data-ttu-id="e158a-147">WCF에서의 인증서 사용에 대한 자세한 내용은 [Working with Certificates](working-with-certificates.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e158a-147">For more information about using certificates in WCF, see [Working with Certificates](working-with-certificates.md).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="e158a-148">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="e158a-148">.NET Framework security</span></span>

<span data-ttu-id="e158a-149">인증서를 마우스 오른쪽 단추로 클릭한 다음 **삭제** 를 클릭하여 **신뢰할 수 있는 루트 인증 기관** 및 **개인** 폴더에서 임시 루트 인증 기관 인증서를 모두 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="e158a-149">Be sure to delete any temporary root authority certificates from the **Trusted Root Certification Authorities** and **Personal** folders by right-clicking the certificate, then clicking **Delete**.</span></span>

## <a name="see-also"></a><span data-ttu-id="e158a-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e158a-150">See also</span></span>

- [<span data-ttu-id="e158a-151">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="e158a-151">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="e158a-152">방법: MMC 스냅인을 사용하여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="e158a-152">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="e158a-153">서비스 및 클라이언트에 보안 설정</span><span class="sxs-lookup"><span data-stu-id="e158a-153">Securing Services and Clients</span></span>](securing-services-and-clients.md)
