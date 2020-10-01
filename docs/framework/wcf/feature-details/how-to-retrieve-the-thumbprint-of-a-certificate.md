---
title: '방법: 인증서 지문 검색'
description: 인증을 위해 인증서를 사용 하는 WCF 응용 프로그램을 개발할 때 필요한 x.509 인증서에 있는 클레임을 지정 하는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], retrieving thumbprint
ms.assetid: da3101aa-78cd-4c34-9652-d1f24777eeab
ms.openlocfilehash: 0622ff9b990dd9d8fe14c4a4c1d48cc8530d5a61
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609475"
---
# <a name="how-to-retrieve-the-thumbprint-of-a-certificate"></a><span data-ttu-id="e16d3-103">방법: 인증서 지문 검색</span><span class="sxs-lookup"><span data-stu-id="e16d3-103">How to: Retrieve the Thumbprint of a Certificate</span></span>
<span data-ttu-id="e16d3-104">인증에 x.509 인증서를 사용 하는 WCF (Windows Communication Foundation) 응용 프로그램을 작성 하는 경우 인증서에 있는 클레임을 지정 해야 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-104">When writing a Windows Communication Foundation (WCF) application that uses an X.509 certificate for authentication, it is often necessary to specify claims found in the certificate.</span></span> <span data-ttu-id="e16d3-105">예를 들어 <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> 메서드에 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 열거를 사용하는 경우 지문 클레임을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-105">For example, you must supply a thumbprint claim when using the <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint> enumeration in the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method.</span></span> <span data-ttu-id="e16d3-106">클레임 값을 찾는 과정은 두 단계로 이루어집니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-106">Finding the claim value requires two steps.</span></span> <span data-ttu-id="e16d3-107">첫째, 인증서에 대한 MMC(Microsoft Management Console) 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-107">First, open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="e16d3-108">[방법: MMC 스냅인을 사용 하 여 인증서 보기](how-to-view-certificates-with-the-mmc-snap-in.md)를 참조 하세요. 두 번째는 여기에 설명 된 대로 적절 한 인증서를 찾고 해당 지문 (또는 기타 클레임 값)을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-108">(See [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).) Second, as described here, find an appropriate certificate and copy its thumbprint (or other claim values).</span></span>  
  
 <span data-ttu-id="e16d3-109">서비스 인증에 인증서를 사용하는 경우 **발급 대상** 열(콘솔의 첫 번째 열)의 값을 확인하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-109">If you are using a certificate for service authentication, it is important to note the value of the **Issued To** column (the first column in the console).</span></span> <span data-ttu-id="e16d3-110">SSL(Secure Sockets Layer)을 전송 보안으로 사용하는 경우 수행되는 첫 번째 확인 작업 중 하나는 서비스의 기본 주소 URI(Uniform Resource Identifier)를 **발급 대상** 값과 비교하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-110">When using Secure Sockets Layer (SSL) as a transport security, one of the first checks done is to compare the base address Uniform Resource Identifier (URI) of a service to the **Issued To** value.</span></span> <span data-ttu-id="e16d3-111">값이 일치해야 하며, 그렇지 않으면 인증 프로세스가 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-111">The values must match or the authentication process is halted.</span></span>  
  
 <span data-ttu-id="e16d3-112">PowerShell New-selfsignedcertificate cmdlet을 사용 하 여 개발 중에만 사용할 임시 인증서를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-112">You can also use the PowerShell New-SelfSignedCertificate cmdlet to create temporary certificates for use only during development.</span></span> <span data-ttu-id="e16d3-113">그러나 이러한 인증서는 기본적으로 인증 기관에서 발급 되지 않으며 프로덕션 용도로는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-113">By default, however, such a certificate is not issued by a certification authority and is unusable for production purposes.</span></span> <span data-ttu-id="e16d3-114">자세한 내용은 [방법: 개발 하는 동안 사용할 임시 인증서 만들기](how-to-create-temporary-certificates-for-use-during-development.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e16d3-114">For more information, see [How to: Create Temporary Certificates for Use During Development](how-to-create-temporary-certificates-for-use-during-development.md).</span></span>  
  
### <a name="to-retrieve-a-certificates-thumbprint"></a><span data-ttu-id="e16d3-115">인증서의 지문을 검색하려면</span><span class="sxs-lookup"><span data-stu-id="e16d3-115">To retrieve a certificate's thumbprint</span></span>  
  
1. <span data-ttu-id="e16d3-116">인증서에 대한 MMC(Microsoft Management Console) 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-116">Open the Microsoft Management Console (MMC) snap-in for certificates.</span></span> <span data-ttu-id="e16d3-117">[How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e16d3-117">(See [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).)</span></span>  
  
2. <span data-ttu-id="e16d3-118">**콘솔 루트** 창의 왼쪽 창에서 **인증서(로컬 컴퓨터)** 를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-118">In the **Console Root** window's left pane, click **Certificates (Local Computer)**.</span></span>  
  
3. <span data-ttu-id="e16d3-119">**개인** 폴더를 클릭하여 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-119">Click the **Personal** folder to expand it.</span></span>  
  
4. <span data-ttu-id="e16d3-120">**인증서** 폴더를 클릭하여 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-120">Click the **Certificates** folder to expand it.</span></span>  
  
5. <span data-ttu-id="e16d3-121">인증서 목록에서 **용도** 제목을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-121">In the list of certificates, note the **Intended Purposes** heading.</span></span> <span data-ttu-id="e16d3-122">**클라이언트 인증** 을 용도로 표시하는 인증서를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-122">Find a certificate that lists **Client Authentication** as an intended purpose.</span></span>  
  
6. <span data-ttu-id="e16d3-123">인증서를 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-123">Double-click the certificate.</span></span>  
  
7. <span data-ttu-id="e16d3-124">**인증서** 대화 상자에서 **자세히** 탭을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-124">In the **Certificate** dialog box, click the **Details** tab.</span></span>  
  
8. <span data-ttu-id="e16d3-125">필드 목록을 스크롤하여 **지문**을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-125">Scroll through the list of fields and click **Thumbprint**.</span></span>  
  
9. <span data-ttu-id="e16d3-126">상자에서 16진수 문자를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-126">Copy the hexadecimal characters from the box.</span></span> <span data-ttu-id="e16d3-127">`X509FindType`에 대한 코드에서 이 지문을 사용하는 경우 16진수 사이의 공백을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-127">If this thumbprint is used in code for the `X509FindType`, remove the spaces between the hexadecimal numbers.</span></span> <span data-ttu-id="e16d3-128">예를 들어 지문 "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b"는 코드에서 "a909502dd82ae41433e6f83886b00d4277a32a7b"로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e16d3-128">For example, the thumbprint "a9 09 50 2d d8 2a e4 14 33 e6 f8 38 86 b0 0d 42 77 a3 2a 7b" should be specified as "a909502dd82ae41433e6f83886b00d4277a32a7b" in code.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16d3-129">참조</span><span class="sxs-lookup"><span data-stu-id="e16d3-129">See also</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509FindType.FindByThumbprint>
- <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A>
- [<span data-ttu-id="e16d3-130">방법: SSL 인증서를 사용하여 포트 구성</span><span class="sxs-lookup"><span data-stu-id="e16d3-130">How to: Configure a Port with an SSL Certificate</span></span>](how-to-configure-a-port-with-an-ssl-certificate.md)
- [<span data-ttu-id="e16d3-131">방법: MMC 스냅인을 사용하여 인증서 보기</span><span class="sxs-lookup"><span data-stu-id="e16d3-131">How to: View Certificates with the MMC Snap-in</span></span>](how-to-view-certificates-with-the-mmc-snap-in.md)
- [<span data-ttu-id="e16d3-132">방법: 개발 중에 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="e16d3-132">How to: Create Temporary Certificates for Use During Development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
