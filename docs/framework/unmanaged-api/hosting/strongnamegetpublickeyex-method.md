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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 7cb1f55e1d8643feb2750e8ea468f608dc3d5d40
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59212065"
---
# <a name="strongnamegetpublickeyex-method"></a><span data-ttu-id="d16e3-102">StrongNameGetPublicKeyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="d16e3-102">StrongNameGetPublicKeyEx Method</span></span>
<span data-ttu-id="d16e3-103">공개/개인 키 쌍에서 공개 키를 가져옵니다 하 고 해시 알고리즘 및 서명 알고리즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-103">Gets the public key from a public/private key pair, and specifies a hash algorithm and a signature algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d16e3-104">구문</span><span class="sxs-lookup"><span data-stu-id="d16e3-104">Syntax</span></span>  
  
```  
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
  
## <a name="parameters"></a><span data-ttu-id="d16e3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d16e3-105">Parameters</span></span>  
 `pwzKeyContainer`  
 <span data-ttu-id="d16e3-106">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-106">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="d16e3-107">하는 경우 `pbKeyBlob` 이 null 이면 `szKeyContainer` 암호화 서비스 공급자 (CSP) 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-107">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the cryptographic service provider (CSP).</span></span> <span data-ttu-id="d16e3-108">이 경우에 `StrongNameGetPublicKeyEx` 메서드 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-108">In this case, the `StrongNameGetPublicKeyEx` method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="d16e3-109">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-109">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="d16e3-110">키에는 1024 비트 adleman의 Rivest-Shamir (RSA) 키를 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-110">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="d16e3-111">다른 종류의 키이 이번에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-111">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="d16e3-112">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-112">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="d16e3-113">이 쌍이 win32 만들어진 형식을 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-113">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="d16e3-114">하는 경우 `pbKeyBlob` 가 null 이면 지정 된 키 컨테이너 `szKeyContainer` 키 쌍을 포함 하도록 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-114">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="d16e3-115">[in] 크기 (바이트)의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-115">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="d16e3-116">[out] 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-116">[out] The returned public key BLOB.</span></span> <span data-ttu-id="d16e3-117">`ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-117">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="d16e3-118">호출자에 게 사용 하 여 메모리를 해제 해야 합니다 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="d16e3-118">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="d16e3-119">[out] 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-119">[out] The size of the returned public key BLOB.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="d16e3-120">[in] 어셈블리 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-120">[in] The assembly hash algorithm.</span></span> <span data-ttu-id="d16e3-121">허용 되는 값의 목록은 설명 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d16e3-121">See the Remarks section for a list of accepted values.</span></span>  
  
 `uReserved`  
 <span data-ttu-id="d16e3-122">[in] 사용 하도록 예약 됩니다. 기본값은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-122">[in] Reserved for future use; defaults to null.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d16e3-123">반환 값</span><span class="sxs-lookup"><span data-stu-id="d16e3-123">Return Value</span></span>  
 `S_OK` <span data-ttu-id="d16e3-124">메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="d16e3-124">if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d16e3-125">설명</span><span class="sxs-lookup"><span data-stu-id="d16e3-125">Remarks</span></span>  
 <span data-ttu-id="d16e3-126">공개 키에 포함 된 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-126">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d16e3-127">설명</span><span class="sxs-lookup"><span data-stu-id="d16e3-127">Remarks</span></span>  
 <span data-ttu-id="d16e3-128">다음 테이블에 대 한 허용 되는 값 집합을 보여 줍니다.는 `uHashAlgId` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d16e3-128">The following table shows the set of accepted values for the `uHashAlgId` parameter.</span></span>  
  
|<span data-ttu-id="d16e3-129">이름</span><span class="sxs-lookup"><span data-stu-id="d16e3-129">Name</span></span>|<span data-ttu-id="d16e3-130">값</span><span class="sxs-lookup"><span data-stu-id="d16e3-130">Value</span></span>|  
|----------|-----------|  
|<span data-ttu-id="d16e3-131">없음</span><span class="sxs-lookup"><span data-stu-id="d16e3-131">None</span></span>|<span data-ttu-id="d16e3-132">0</span><span class="sxs-lookup"><span data-stu-id="d16e3-132">0</span></span>|  
|<span data-ttu-id="d16e3-133">SHA-1</span><span class="sxs-lookup"><span data-stu-id="d16e3-133">SHA-1</span></span>|<span data-ttu-id="d16e3-134">0x8004</span><span class="sxs-lookup"><span data-stu-id="d16e3-134">0x8004</span></span>|  
|<span data-ttu-id="d16e3-135">SHA-256</span><span class="sxs-lookup"><span data-stu-id="d16e3-135">SHA-256</span></span>|<span data-ttu-id="d16e3-136">0x800c</span><span class="sxs-lookup"><span data-stu-id="d16e3-136">0x800c</span></span>|  
|<span data-ttu-id="d16e3-137">SHA-384</span><span class="sxs-lookup"><span data-stu-id="d16e3-137">SHA-384</span></span>|<span data-ttu-id="d16e3-138">0x800d</span><span class="sxs-lookup"><span data-stu-id="d16e3-138">0x800d</span></span>|  
|<span data-ttu-id="d16e3-139">SHA-512</span><span class="sxs-lookup"><span data-stu-id="d16e3-139">SHA-512</span></span>|<span data-ttu-id="d16e3-140">0x800e</span><span class="sxs-lookup"><span data-stu-id="d16e3-140">0x800e</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d16e3-141">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d16e3-141">Requirements</span></span>  
 <span data-ttu-id="d16e3-142">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d16e3-142">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d16e3-143">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="d16e3-143">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="d16e3-144">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d16e3-144">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="d16e3-145">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="d16e3-145">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="d16e3-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="d16e3-146">See also</span></span>

- [<span data-ttu-id="d16e3-147">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="d16e3-147">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="d16e3-148">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="d16e3-148">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="d16e3-149">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d16e3-149">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
- [<span data-ttu-id="d16e3-150">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="d16e3-150">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
