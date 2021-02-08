---
description: '자세한 정보: Authenticode(관리되지 않는 API 참조)'
title: Authenticode(관리되지 않는 API 참조)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: d7a1684fde900bfc01161193d0747b156c6856a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772837"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="53462-103">Authenticode(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="53462-103">Authenticode (Unmanaged API Reference)</span></span>

<span data-ttu-id="53462-104">Authenticode XrML 라이센스 만들기 및 확인 모듈을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-104">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="53462-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="53462-105">In This Section</span></span>  

 [<span data-ttu-id="53462-106">_AxlGetIssuerPublicKeyHash 함수</span><span class="sxs-lookup"><span data-stu-id="53462-106">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="53462-107">지정한 인증서에 서명하는 데 사용되는 프라이빗 키에 연결된 퍼블릭 키의 SHA-1 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-107">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="53462-108">_AxlPublicKeyBlobToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="53462-108">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="53462-109">CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-109">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="53462-110">_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="53462-110">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="53462-111">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-111">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="53462-112">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="53462-112">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="53462-113">AXL_AUTHENTICODE_SIGNER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-113">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="53462-114">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="53462-114">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="53462-115">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-115">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="53462-116">CertTimestampAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="53462-116">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="53462-117">CertCreateAuthenticodeLicense에 의해 작성된 Authenticode XrML 라이선스에 타임스탬프를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-117">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="53462-118">CertVerifyAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="53462-118">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="53462-119">Authenticode XrML 라이선스의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-119">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="53462-120">AXL_AUTHENTICODE_SIGNER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="53462-120">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="53462-121">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-121">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="53462-122">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="53462-122">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="53462-123">Authenticode 타임스탬퍼 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="53462-123">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="53462-124">참조</span><span class="sxs-lookup"><span data-stu-id="53462-124">See also</span></span>

- [<span data-ttu-id="53462-125">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="53462-125">Unmanaged API Reference</span></span>](../index.md)
