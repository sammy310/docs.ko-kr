---
description: '자세히 알아보기: CertVerifyAuthenticodeLicense 함수'
title: CertVerifyAuthenticodeLicense 함수
ms.date: 03/30/2017
api_name:
- CertVerifyAuthenticodeLicense
api_location:
- clr.dll
api_type:
- DLLExport
ms.assetid: 00118de7-33c6-41c4-8e1f-5d5e35e0da83
topic_type:
- apiref
ms.openlocfilehash: 0174223a4c1b984bf2d5d957219a85230fef8d0e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99772850"
---
# <a name="certverifyauthenticodelicense-function"></a><span data-ttu-id="2e060-103">CertVerifyAuthenticodeLicense 함수</span><span class="sxs-lookup"><span data-stu-id="2e060-103">CertVerifyAuthenticodeLicense Function</span></span>

<span data-ttu-id="2e060-104">Authenticode XrML 라이선스의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-104">Verifies the validity of an Authenticode XrML license.</span></span>

## <a name="syntax"></a><span data-ttu-id="2e060-105">구문</span><span class="sxs-lookup"><span data-stu-id="2e060-105">Syntax</span></span>

```cpp
HRESULT CertVerifyAuthenticodeLicense (
    [in]   PCRYPT_DATA_BLOB                   pLicenseBlob,
    [in]   OPTIONAL DWORD                     dwFlags,
    [out]  PAXL_AUTHENTICODE_SIGNER_INFO      pSignerInfo,
    [out]  PAXL_AUTHENTICODE_TIMESTAMPER_INFO pTimestamperInfo
);
```

## <a name="parameters"></a><span data-ttu-id="2e060-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2e060-106">Parameters</span></span>

 `pLicenseBlob`\
 <span data-ttu-id="2e060-107">[in] 확인할 Authenticode XrML 라이선스입니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-107">[in] The Authenticode XrML license to be verified.</span></span>

 <span data-ttu-id="2e060-108">[CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) 구조체를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2e060-108">See the [CRYPTOAPI_BLOB](/windows/win32/api/dpapi/ns-dpapi-crypt_integer_blob) structure.</span></span>

 `dwFlags`\
 <span data-ttu-id="2e060-109">[in] 선택적 항목으로,</span><span class="sxs-lookup"><span data-stu-id="2e060-109">[in] Optional.</span></span> <span data-ttu-id="2e060-110">다음 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-110">A combination of following values:</span></span>

- <span data-ttu-id="2e060-111">AXL_REVOCATION_NO_CHECK</span><span class="sxs-lookup"><span data-stu-id="2e060-111">AXL_REVOCATION_NO_CHECK</span></span>

- <span data-ttu-id="2e060-112">AXL_REVOCATION_CHECK_END_CERT_ONLY</span><span class="sxs-lookup"><span data-stu-id="2e060-112">AXL_REVOCATION_CHECK_END_CERT_ONLY</span></span>

- <span data-ttu-id="2e060-113">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span><span class="sxs-lookup"><span data-stu-id="2e060-113">AXL_REVOCATION_CHECK_ENTIRE_CHAIN</span></span>

- <span data-ttu-id="2e060-114">AXL_URL_CACHE_ONLY_RETRIEVAL</span><span class="sxs-lookup"><span data-stu-id="2e060-114">AXL_URL_CACHE_ONLY_RETRIEVAL</span></span>

- <span data-ttu-id="2e060-115">AXL_LIFETIME_SIGNING</span><span class="sxs-lookup"><span data-stu-id="2e060-115">AXL_LIFETIME_SIGNING</span></span>

- <span data-ttu-id="2e060-116">AXL_TRUST_MICROSOFT_ROOT_ONLY</span><span class="sxs-lookup"><span data-stu-id="2e060-116">AXL_TRUST_MICROSOFT_ROOT_ONLY</span></span>

 `pSignerInfo`\
 <span data-ttu-id="2e060-117">[out] 서명자의 정보를 받는 데 사용되는 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-117">[out] To receive the signer's information.</span></span> <span data-ttu-id="2e060-118">라이선스가 서명되지 않은 경우에는 `dwError` 가 TRUST_E_NOSIGNATURE로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-118">If the license wasn't signed, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="2e060-119">사용 후 [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) 함수를 사용 하 여 리소스를 해제 하는 것은 호출자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-119">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeSignerInfo](certfreeauthenticodesignerinfo-function.md) function after use.</span></span>

 <span data-ttu-id="2e060-120">[AXL_AUTHENTICODE_SIGNER_INFO 구조체](axl-authenticode-signer-info-structure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2e060-120">See [AXL_AUTHENTICODE_SIGNER_INFO Structure](axl-authenticode-signer-info-structure.md).</span></span>

 `pTimestamperInfo`\
 <span data-ttu-id="2e060-121">[out] 타임스탬퍼 정보(있는 경우)를 받으려는 경우 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-121">[out] To receive time stamper's information, if available.</span></span> <span data-ttu-id="2e060-122">라이선스에 타임스탬프가 적용되지 않은 경우에는 `dwError` 가 TRUST_E_NOSIGNATURE로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-122">If the license was not time-stamped, `dwError` is set to TRUST_E_NOSIGNATURE.</span></span> <span data-ttu-id="2e060-123">사용 후 [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) 함수를 사용 하 여 리소스를 해제 하는 것은 호출자의 책임입니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-123">It is the caller's responsibility to free resources by using the [CertFreeAuthenticodeTimestamperInfo](certfreeauthenticodetimestamperinfo-function.md) function after use.</span></span>

 <span data-ttu-id="2e060-124">[AXL_AUTHENTICODE_TIMESTAMPER_INFO 구조체](axl-authenticode-timestamper-info-structure.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2e060-124">See [AXL_AUTHENTICODE_TIMESTAMPER_INFO Structure](axl-authenticode-timestamper-info-structure.md).</span></span>

## <a name="return-value"></a><span data-ttu-id="2e060-125">Return Value</span><span class="sxs-lookup"><span data-stu-id="2e060-125">Return Value</span></span>

 <span data-ttu-id="2e060-126">성공하는 경우 `S_OK`가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-126">Returns `S_OK` if successful.</span></span> <span data-ttu-id="2e060-127">그러지 않으면 오류 코드가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e060-127">Otherwise, returns an error code.</span></span>

## <a name="requirements"></a><span data-ttu-id="2e060-128">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2e060-128">Requirements</span></span>

<span data-ttu-id="2e060-129">**어셈블리**: clr.dll</span><span class="sxs-lookup"><span data-stu-id="2e060-129">**Assembly**: clr.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="2e060-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2e060-130">See also</span></span>

- [<span data-ttu-id="2e060-131">Authenticode</span><span class="sxs-lookup"><span data-stu-id="2e060-131">Authenticode</span></span>](index.md)
- [<span data-ttu-id="2e060-132">GetHashFromHandle 메서드</span><span class="sxs-lookup"><span data-stu-id="2e060-132">GetHashFromHandle Method</span></span>](../hosting/iclrstrongname-gethashfromhandle-method.md)
- [<span data-ttu-id="2e060-133">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2e060-133">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
