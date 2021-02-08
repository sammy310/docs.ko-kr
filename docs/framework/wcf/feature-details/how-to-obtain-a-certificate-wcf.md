---
description: '자세한 정보: 방법: 인증서 가져오기 (WCF)'
title: '방법: 인증서 가져오기(WCF)'
ms.date: 03/30/2017
helpviewer_keywords:
- certificates [WCF], obtaining
ms.assetid: d53762fd-15ea-42dc-b0ea-6a6597aa23f7
ms.openlocfilehash: 2ca40c9646bbdeb6c29a94966fd24ec00d9b5306
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99793703"
---
# <a name="how-to-obtain-a-certificate-wcf"></a><span data-ttu-id="87303-103">방법: 인증서 가져오기(WCF)</span><span class="sxs-lookup"><span data-stu-id="87303-103">How to: Obtain a Certificate (WCF)</span></span>

<span data-ttu-id="87303-104">X.509 인증서를 사용 하는의 WCF (Windows Communication Foundation) 기능을 사용 하려면 먼저 인증서를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87303-104">To use any of the Windows Communication Foundation (WCF) features of that use X.509 certificates, you just first obtain certificates.</span></span>  
  
### <a name="to-obtain-an-x509-certificate"></a><span data-ttu-id="87303-105">X.509 인증서를 받으려면</span><span class="sxs-lookup"><span data-stu-id="87303-105">To obtain an X.509 certificate</span></span>  
  
1. <span data-ttu-id="87303-106">다음 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-106">Choose one of the following:</span></span>  
  
    - <span data-ttu-id="87303-107">VeriSign, Inc, 같은 인증 기관에서 인증서를 구입합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-107">Purchase a certificate from a certification authority, such as VeriSign, Inc.</span></span>  
  
    - <span data-ttu-id="87303-108">자체 인증서 서비스를 설정하고 인증 기관이 인증서에 서명하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-108">Set up your own certificate service and have a certification authority sign the certificates.</span></span> <span data-ttu-id="87303-109">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter 및 Windows 2000 Datacenter Server 모두 PKI (공개 키 인프라)를 지 원하는 인증서 서비스를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-109">Windows Server 2003, Windows 2000 Server, Windows 2000 Server Datacenter, and Windows 2000 Datacenter Server all include certificate services that support public key infrastructure (PKI).</span></span> <span data-ttu-id="87303-110">Windows Server 2008에서는 [Active Directory 인증서 서비스](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) 역할을 사용 하 여 인증 기관을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-110">In Windows Server 2008, use the [Active Directory Certificate Services](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731564(v=ws.10)) role to manage a certification authority.</span></span>  
  
    - <span data-ttu-id="87303-111">자체 인증서 서비스를 설정하고 인증서가 서명되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-111">Set up your own certificate service and do not have the certificates signed.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="87303-112">어떤 방법을 선택하든 관계없이 X.509 인증서를 포함하는 SOAP 요청의 수신자는 X.509 인증서를 신뢰해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-112">Whichever approach you take, the recipient of the SOAP request that contains the X.509 certificate must trust the X.509 certificate.</span></span> <span data-ttu-id="87303-113">이는 X.509 인증서나 인증서 체인의 발급자가 신뢰된 사용자 인증서에 있고 X.509 인증서가 신뢰되지 않은 인증서 저장소에 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="87303-113">This means that the X.509 certificate or an issuer in the certificate chain is in the Trusted People certificate store and that the X.509 certificate is not in the Untrusted Certificates store.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87303-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87303-114">See also</span></span>

- [<span data-ttu-id="87303-115">인증서 사용</span><span class="sxs-lookup"><span data-stu-id="87303-115">Working with Certificates</span></span>](working-with-certificates.md)
- [<span data-ttu-id="87303-116">방법: 개발 중에 사용할 임시 인증서 만들기</span><span class="sxs-lookup"><span data-stu-id="87303-116">How to: Create Temporary Certificates for Use During Development</span></span>](how-to-create-temporary-certificates-for-use-during-development.md)
