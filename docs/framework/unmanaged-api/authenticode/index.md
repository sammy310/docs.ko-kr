---
description: '자세한 정보: Authenticode(관리되지 않는 API 참조)'
title: Authenticode(관리되지 않는 API 참조)
ms.date: 03/30/2017
ms.assetid: 7e8cc303-6e77-4116-aa8b-7ea297a3a467
ms.openlocfilehash: 0a4a9b4ba3cc9a5818896508c80bc31073f514e7
ms.sourcegitcommit: 26721a2260deabb3318cc98af8619306711153cd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "105027846"
---
# <a name="authenticode-unmanaged-api-reference"></a><span data-ttu-id="69b57-103">Authenticode(관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="69b57-103">Authenticode (Unmanaged API Reference)</span></span>

<span data-ttu-id="69b57-104">Authenticode XrML 라이센스 만들기 및 확인 모듈을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-104">Supports the Authenticode XrML license creation and verification module.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="69b57-105">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="69b57-105">In This Section</span></span>  

 [<span data-ttu-id="69b57-106">_AxlGetIssuerPublicKeyHash 함수</span><span class="sxs-lookup"><span data-stu-id="69b57-106">_AxlGetIssuerPublicKeyHash Function</span></span>](axlgetissuerpublickeyhash-function.md)  
 <span data-ttu-id="69b57-107">지정한 인증서에 서명하는 데 사용되는 프라이빗 키에 연결된 퍼블릭 키의 SHA-1 해시를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-107">Retrieves the SHA-1 hash of the public key associated with the private key that is used to sign the specified certificate.</span></span>  
  
 [<span data-ttu-id="69b57-108">_AxlPublicKeyBlobToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="69b57-108">_AxlPublicKeyBlobToPublicKeyToken Function</span></span>](axlpublickeyblobtopublickeytoken-function.md)  
 <span data-ttu-id="69b57-109">CSP PUBLICKEYBLOB 형식에서 강력한 이름 공개 키 토큰을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-109">Computes the strong name public key token from a CSP PUBLICKEYBLOB format.</span></span>  
  
 [<span data-ttu-id="69b57-110">_AxlRSAKeyValueToPublicKeyToken 함수</span><span class="sxs-lookup"><span data-stu-id="69b57-110">_AxlRSAKeyValueToPublicKeyToken Function</span></span>](axlrsakeyvaluetopublickeytoken-function.md)  
 <span data-ttu-id="69b57-111">모듈러스 및 지수를 강력한 이름 공개 키 토큰으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-111">Converts a Modulus and Exponent to a strong name public key token.</span></span>  
  
 [<span data-ttu-id="69b57-112">CertFreeAuthenticodeSignerInfo 함수</span><span class="sxs-lookup"><span data-stu-id="69b57-112">CertFreeAuthenticodeSignerInfo Function</span></span>](certfreeauthenticodesignerinfo-function.md)  
 <span data-ttu-id="69b57-113">AXL_AUTHENTICODE_SIGNER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-113">Frees resources allocated for the AXL_AUTHENTICODE_SIGNER_INFO structure.</span></span>  
  
 [<span data-ttu-id="69b57-114">CertFreeAuthenticodeTimestamperInfo 함수</span><span class="sxs-lookup"><span data-stu-id="69b57-114">CertFreeAuthenticodeTimestamperInfo Function</span></span>](certfreeauthenticodetimestamperinfo-function.md)  
 <span data-ttu-id="69b57-115">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체에 할당된 리소스를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-115">Frees resources allocated for the AXL_AUTHENTICODE_TIMESTAMPER_INFO structure.</span></span>  
  
 [<span data-ttu-id="69b57-116">CertTimestampAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="69b57-116">CertTimestampAuthenticodeLicense Function</span></span>](certtimestampauthenticodelicense-function.md)  
 <span data-ttu-id="69b57-117">CertCreateAuthenticodeLicense에 의해 작성된 Authenticode XrML 라이선스에 타임스탬프를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-117">Time stamps an Authenticode XrML license created by CertCreateAuthenticodeLicense.</span></span>  
  
 [<span data-ttu-id="69b57-118">CertVerifyAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="69b57-118">CertVerifyAuthenticodeLicense Function</span></span>](certverifyauthenticodelicense-function.md)  
 <span data-ttu-id="69b57-119">Authenticode XrML 라이선스의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-119">Verifies the validity of an Authenticode XrML license.</span></span>  
  
 [<span data-ttu-id="69b57-120">AXL_AUTHENTICODE_SIGNER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="69b57-120">AXL_AUTHENTICODE_SIGNER_INFO Structure</span></span>](axl-authenticode-signer-info-structure.md)  
 <span data-ttu-id="69b57-121">Authenticode 서명자 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-121">Defines the Authenticode signer information.</span></span>  
  
 [<span data-ttu-id="69b57-122">AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조</span><span class="sxs-lookup"><span data-stu-id="69b57-122">AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure</span></span>](axl-authenticode-timestamper-info-structure.md)  
 <span data-ttu-id="69b57-123">Authenticode 타임스탬퍼 정보를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="69b57-123">Defines the Authenticode time stamper information.</span></span>  

## <a name="requirements"></a><span data-ttu-id="69b57-124">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69b57-124">Requirements</span></span>

<span data-ttu-id="69b57-125">**라이브러리**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="69b57-125">**Library**: clr.dll</span></span>
  
## <a name="see-also"></a><span data-ttu-id="69b57-126">참조</span><span class="sxs-lookup"><span data-stu-id="69b57-126">See also</span></span>

- [<span data-ttu-id="69b57-127">관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="69b57-127">Unmanaged API Reference</span></span>](../index.md)
