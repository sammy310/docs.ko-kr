---
title: StrongNameGetPublicKeyEx 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName2.StrongNameGetPublicKeyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- StrongNameGetPublicKeyEx
helpviewer_keywords:
- StrongNameGetPublicKeyEx method, ICLRStrongName2 interface [.NET Framework hosting]
- ICLRStrongName2::StrongNameGetPublicKeyEx method [.NET Framework hosting]
ms.assetid: 63d8260c-fb32-4f8f-a357-768afd570f68
topic_type:
- apiref
ms.openlocfilehash: 93afe1afd9ea9637d039a8b4a4e81267d49c08b6
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176229"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="a585a-102">StrongNameGetPublicKeyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="a585a-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="a585a-103">공개/개인 키 쌍에서 공개 키를 가져옵니다 및 해시 알고리즘 및 서명 알고리즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a585a-104">구문</span><span class="sxs-lookup"><span data-stu-id="a585a-104">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   pwzKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
    [in]  ULONG     uHashAlgId,  
    [in]  ULONG     uReserved,  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a585a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a585a-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="a585a-106">【인】 공개/개인 키 쌍을 포함하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="a585a-107">null인 `pbKeyBlob` `szKeyContainer` 경우 CSP(암호화 서비스 공급자) 내에서 유효한 컨테이너를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="a585a-108">이 경우 `StrongNameGetPublicKeyEx` 메서드는 컨테이너에 저장된 키 쌍에서 공개 키를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="a585a-109">null이 아닌 경우 `pbKeyBlob` 키 쌍은 키 이진 큰 개체(BLOB)에 포함되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="a585a-110">키는 1024비트 Rivest-Shamir-Adleman(RSA) 서명 키여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="a585a-111">현재 다른 유형의 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="a585a-112">【인】 공용/개인 키 쌍에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="a585a-113">이 쌍은 Win32 `CryptExportKey` 함수에서 만든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="a585a-114">null인 경우 `pbKeyBlob` 지정한 `szKeyContainer` 키 컨테이너는 키 쌍을 포함하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="a585a-115">【인】 의 크기(바이트)입니다. `pbKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="a585a-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="a585a-116">【아웃】 반환된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="a585a-117">매개 `ppbPublicKeyBlob` 변수는 공통 언어 런타임에 의해 할당되고 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="a585a-118">호출자는 [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용하여 메모리를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="a585a-119">【아웃】 반환된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="a585a-120">【인】 어셈블리 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="a585a-121">수락된 값 목록은 비고 섹션을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a585a-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="a585a-122">【인】 향후 사용을 위해 예약; 기본값은 null로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a585a-123">Return Value</span><span class="sxs-lookup"><span data-stu-id="a585a-123">Return Value</span></span>  
 <span data-ttu-id="a585a-124">`S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="a585a-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a585a-125">설명</span><span class="sxs-lookup"><span data-stu-id="a585a-125">Remarks</span></span>  
 <span data-ttu-id="a585a-126">공개 키는 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a585a-127">설명</span><span class="sxs-lookup"><span data-stu-id="a585a-127">Remarks</span></span>  
 <span data-ttu-id="a585a-128">다음 표에서는 매개 변수에 대해 `uHashAlgId` 허용된 값 집합을 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="a585a-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="a585a-129">속성</span><span class="sxs-lookup"><span data-stu-id="a585a-129">Name</span></span>|<span data-ttu-id="a585a-130">값</span><span class="sxs-lookup"><span data-stu-id="a585a-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="a585a-131">None</span><span class="sxs-lookup"><span data-stu-id="a585a-131">None</span></span>|<span data-ttu-id="a585a-132">0</span><span class="sxs-lookup"><span data-stu-id="a585a-132">0</span></span>|  
|<span data-ttu-id="a585a-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="a585a-133">SHA-1</span></span>|<span data-ttu-id="a585a-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="a585a-134">0x8004</span></span>|  
|<span data-ttu-id="a585a-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="a585a-135">SHA-256</span></span>|<span data-ttu-id="a585a-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="a585a-136">0x800c</span></span>|  
|<span data-ttu-id="a585a-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="a585a-137">SHA-384</span></span>|<span data-ttu-id="a585a-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="a585a-138">0x800d</span></span>|  
|<span data-ttu-id="a585a-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="a585a-139">SHA-512</span></span>|<span data-ttu-id="a585a-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="a585a-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a585a-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a585a-141">Requirements</span></span>  
 <span data-ttu-id="a585a-142">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a585a-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a585a-143">**헤더:** 메타호스트</span><span class="sxs-lookup"><span data-stu-id="a585a-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="a585a-144">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="a585a-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a585a-145">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a585a-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a585a-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a585a-146">See also</span></span>

- [<span data-ttu-id="a585a-147">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="a585a-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="a585a-148">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="a585a-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="a585a-149">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a585a-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="a585a-150">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="a585a-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
