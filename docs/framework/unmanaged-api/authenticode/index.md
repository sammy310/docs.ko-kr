---
title: Authenticode(관리되지 않는 API 참조)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 9b3e1585278bda82dedf7542e866a551867b9c9f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95674049"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="91a92-102">Authenticode(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="91a92-102">Authenticode (Unmanaged API Reference)</span></span>

<span data-ttu-id="91a92-103">Authenticode XrML 라이센스 만들기 및 확인 모듈을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-103">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="91a92-104">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="91a92-104">In This Section</span></span>  

 [<span data-ttu-id="91a92-105">_AxlGetIssuerPublicKeyHash 함수</span><span class="sxs-lookup"><span data-stu-id="91a92-105">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="91a92-106">지정한 인증서에 서명하는 데 사용되는 프라이빗 키에 연결된 퍼블릭 키의 SHA-1 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-106">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="91a92-107">_AxlPublicKeyBlobToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="91a92-107">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="91a92-108">CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-108">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="91a92-109">_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="91a92-109">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="91a92-110">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-110">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="91a92-111">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="91a92-111">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="91a92-112">AXL_AUTHENTICODE_SIGNER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-112">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="91a92-113">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="91a92-113">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="91a92-114">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-114">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="91a92-115">CertTimestampAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="91a92-115">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="91a92-116">CertCreateAuthenticodeLicense에 의해 작성된 Authenticode XrML 라이선스에 타임스탬프를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-116">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="91a92-117">CertVerifyAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="91a92-117">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="91a92-118">Authenticode XrML 라이선스의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-118">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="91a92-119">AXL_AUTHENTICODE_SIGNER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="91a92-119">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="91a92-120">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-120">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="91a92-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="91a92-121">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="91a92-122">Authenticode 타임스탬퍼 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="91a92-122">Defines the Authenticode time stamper information.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91a92-123">참조</span><span class="sxs-lookup"><span data-stu-id="91a92-123">See also</span></span>

- [<span data-ttu-id="91a92-124">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="91a92-124">Unmanaged API Reference</span></span>](../index.md)
