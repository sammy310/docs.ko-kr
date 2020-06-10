---
title: '방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], specifying the certificate authority certificate chain
- certificates [WCF], verifying signatures
ms.assetid: 7c719355-aa41-4567-80d0-5115a8cf73fd
ms.openlocfilehash: 103d68d4ccb4cc243d28037260c1f9f380485ff6
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84600311"
---
# <a name="how-to-specify-the-certificate-authority-certificate-chain-used-to-verify-signatures-wcf"></a><span data-ttu-id="a0194-102">방법: 서명을 확인하는 데 사용되는 인증 기관 인증서 체인 지정(WCF)</span><span class="sxs-lookup"><span data-stu-id="a0194-102">How to: Specify the Certificate Authority Certificate Chain Used to Verify Signatures (WCF)</span></span>
<span data-ttu-id="a0194-103">Windows Communication Foundation (WCF)는 x.509 인증서를 사용 하 여 서명 된 SOAP 메시지를 수신 하는 경우 기본적으로 신뢰할 수 있는 인증 기관에서 x.509 인증서를 발급 했는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-103">When Windows Communication Foundation (WCF) receives a SOAP message signed using an X.509 certificate, by default it verifies that the X.509 certificate was issued by a trusted certification authority.</span></span> <span data-ttu-id="a0194-104">이렇게 하려면 인증서 저장소를 찾고 해당 인증 기관의 인증서가 신뢰할 수 있는 것으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-104">This is done by looking in a certificate store and determining if the certificate for that certification authority has been designated as trusted.</span></span> <span data-ttu-id="a0194-105">WCF가 이러한 결정을 내릴 수 있도록 하려면 올바른 인증서 저장소에 인증 기관 인증서 체인을 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-105">In order for WCF to make this determination, the certification authority certificate chain must be installed in the correct certificate store.</span></span>  
  
### <a name="to-install-a-certification-authority-certificate-chain"></a><span data-ttu-id="a0194-106">인증 기관 인증서 체인을 설치하려면</span><span class="sxs-lookup"><span data-stu-id="a0194-106">To install a certification authority certificate chain</span></span>  
  
- <span data-ttu-id="a0194-107">SOAP 메시지 수신자가에서 발급 한 x.509 인증서를 신뢰 하는 각 인증 기관에 대해 WCF가 x.509 인증서를 검색 하도록 구성 된 인증서 저장소에 인증 기관 인증서 체인을 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-107">For each certification authority that a SOAP message recipient intends to trust X.509 certificates issued from, install the certification authority certificate chain into the certificate store that WCF is configured to retrieve X.509 certificates from.</span></span>  
  
     <span data-ttu-id="a0194-108">예를 들어, SOAP 메시지 받는 사람이 Microsoft에서 발급 한 x.509 인증서를 신뢰 하려는 경우 Microsoft 용 인증 기관 인증서 체인은 WCF가 x.509 인증서를 찾도록 설정 된 인증서 저장소에 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-108">For instance, if a SOAP message recipient intends to trust X.509 certificates issued by Microsoft, the certification authority certificate chain for Microsoft must be installed in the certificate store that WCF is set up to look for X.509 certificates from.</span></span> <span data-ttu-id="a0194-109">WCF가 x.509 인증서를 검색 하는 인증서 저장소는 코드 또는 구성에서 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-109">The certificate store in which WCF looks for X.509 certificates can be specified in code or configuration.</span></span> <span data-ttu-id="a0194-110">예를 들어 메서드를 사용 하 여 코드에서이를 지정 <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> 하거나를 비롯 한 몇 가지 방법을 구성에서 지정할 수 있습니다 [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span><span class="sxs-lookup"><span data-stu-id="a0194-110">For example, this can be specified in code using the <xref:System.ServiceModel.Security.X509CertificateInitiatorClientCredential.SetCertificate%2A> method or in configuration a few ways, including the [\<serviceCertificate>](../../configure-apps/file-schema/wcf/servicecertificate-of-clientcredentials-element.md) .</span></span>  
  
     <span data-ttu-id="a0194-111">Windows는 신뢰할 수 있는 인증 기관에 대한 기본 인증서 체인 집합이 함께 제공되므로 모든 인증 기관에 대한 인증서 체인을 반드시 설치할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-111">Because Windows ships with a set of default certificate chains for trusted certificate authorities, it may not be necessary to install the certificate chain for all certificate authorities.</span></span>  
  
    1. <span data-ttu-id="a0194-112">인증 기관 인증서 체인을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-112">Export the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="a0194-113">이 작업을 수행하는 방법은 인증 기관에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-113">Exactly how this is done depends on the certification authority.</span></span> <span data-ttu-id="a0194-114">인증 기관에서 Microsoft 인증서 서비스를 실행 하는 경우 **ca 인증서, 인증서 체인 또는 CRL 다운로드**를 선택한 다음 **ca 인증서 다운로드**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-114">If the certification authority is running Microsoft Certificate Services, select **Download a CA certificate, certificate chain, or CRL**, and then choose **Download CA certificate**.</span></span>  
  
    2. <span data-ttu-id="a0194-115">인증 기관 인증서 체인을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-115">Import the certification authority certificate chain.</span></span>  
  
         <span data-ttu-id="a0194-116">MMC(Microsoft Management Console)에서 인증서 스냅인을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-116">In the Microsoft Management Console (MMC), open the Certificates snap-in.</span></span> <span data-ttu-id="a0194-117">WCF가 x.509 인증서를 검색 하도록 구성 된 인증서 저장소에 대해 **신뢰할 수 있는 루트** **인증 기관** 폴더를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-117">For the certificate store that WCF is configured to retrieve X.509 certificates from, select the **Trusted Root** **Certification Authorities** folder.</span></span> <span data-ttu-id="a0194-118">**신뢰할 수 있는 루트 인증 기관** 폴더에서 **인증서** 폴더를 마우스 오른쪽 단추로 클릭 하 고 **모든 작업**을 가리킨 다음 **가져오기**를 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-118">Under the **Trusted Root Certification Authorities** folder, right-click the **Certificates** folder, point to **All Tasks**, and then click **Import**.</span></span> <span data-ttu-id="a0194-119">a 단계에서 내보낸 파일을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a0194-119">Provide the file exported in step a.</span></span>  
  
         <span data-ttu-id="a0194-120">MMC에서 인증서 스냅인을 사용 하는 방법에 대 한 자세한 내용은 [방법: Mmc 스냅인을 사용 하 여 인증서 보기](how-to-view-certificates-with-the-mmc-snap-in.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a0194-120">For more information about using the Certificates snap-in with MMC, see [How to: View Certificates with the MMC Snap-in](how-to-view-certificates-with-the-mmc-snap-in.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a0194-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a0194-121">See also</span></span>

- [<span data-ttu-id="a0194-122">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="a0194-122">Working with Certificates</span></span>](working-with-certificates.md)
