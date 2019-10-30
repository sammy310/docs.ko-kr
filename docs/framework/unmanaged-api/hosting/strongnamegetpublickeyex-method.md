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
ms.openlocfilehash: 700bcc5b818c452d3642d325fb6fe19cbb162474
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141448"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="b31df-102">StrongNameGetPublicKeyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="b31df-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="b31df-103">공개/개인 키 쌍에서 공개 키를 가져오고 해시 알고리즘과 서명 알고리즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b31df-104">구문</span><span class="sxs-lookup"><span data-stu-id="b31df-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b31df-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b31df-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="b31df-106">진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="b31df-107">`pbKeyBlob`가 null 인 경우에는 CSP (암호화 서비스 공급자) 내에 올바른 컨테이너를 지정 해야 `szKeyContainer`.</span><span class="sxs-lookup"><span data-stu-id="b31df-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="b31df-108">이 경우 `StrongNameGetPublicKeyEx` 메서드는 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="b31df-109">`pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="b31df-110">키는 1024 비트 RSA (Rivest Rivest-shamir-adleman Rivest-shamir-adleman) 서명 키 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="b31df-111">지금은 다른 유형의 키를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="b31df-112">진행 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="b31df-113">이 쌍은 Win32 `CryptExportKey` 함수에 의해 생성 된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="b31df-114">`pbKeyBlob` null 인 경우 `szKeyContainer`에 의해 지정 된 키 컨테이너는 키 쌍을 포함 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="b31df-115">진행 `pbKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="b31df-116">제한이 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="b31df-117">`ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="b31df-118">호출자는 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 하 여 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="b31df-119">제한이 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="b31df-120">진행 어셈블리 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="b31df-121">허용 되는 값 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b31df-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="b31df-122">진행 나중에 사용 하도록 예약 되어 있습니다. 기본값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b31df-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="b31df-123">Return Value</span></span>  
 <span data-ttu-id="b31df-124">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](https://go.microsoft.com/fwlink/?LinkId=213878) 참조).</span><span class="sxs-lookup"><span data-stu-id="b31df-124">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b31df-125">주의</span><span class="sxs-lookup"><span data-stu-id="b31df-125">Remarks</span></span>  
 <span data-ttu-id="b31df-126">공개 키가 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b31df-127">주의</span><span class="sxs-lookup"><span data-stu-id="b31df-127">Remarks</span></span>  
 <span data-ttu-id="b31df-128">다음 표에서는 `uHashAlgId` 매개 변수에 대해 허용 되는 값 집합을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="b31df-129">name</span><span class="sxs-lookup"><span data-stu-id="b31df-129">Name</span></span>|<span data-ttu-id="b31df-130">값</span><span class="sxs-lookup"><span data-stu-id="b31df-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="b31df-131">없음</span><span class="sxs-lookup"><span data-stu-id="b31df-131">None</span></span>|<span data-ttu-id="b31df-132">0</span><span class="sxs-lookup"><span data-stu-id="b31df-132">0</span></span>|  
|<span data-ttu-id="b31df-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="b31df-133">SHA-1</span></span>|<span data-ttu-id="b31df-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="b31df-134">0x8004</span></span>|  
|<span data-ttu-id="b31df-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="b31df-135">SHA-256</span></span>|<span data-ttu-id="b31df-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="b31df-136">0x800c</span></span>|  
|<span data-ttu-id="b31df-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="b31df-137">SHA-384</span></span>|<span data-ttu-id="b31df-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="b31df-138">0x800d</span></span>|  
|<span data-ttu-id="b31df-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="b31df-139">SHA-512</span></span>|<span data-ttu-id="b31df-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="b31df-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b31df-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b31df-141">Requirements</span></span>  
 <span data-ttu-id="b31df-142">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b31df-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b31df-143">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="b31df-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b31df-144">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b31df-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b31df-145">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b31df-145">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b31df-146">참조</span><span class="sxs-lookup"><span data-stu-id="b31df-146">See also</span></span>

- [<span data-ttu-id="b31df-147">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="b31df-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="b31df-148">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="b31df-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="b31df-149">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b31df-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="b31df-150">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="b31df-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
