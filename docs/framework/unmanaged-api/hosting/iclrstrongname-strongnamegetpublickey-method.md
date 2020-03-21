---
title: ICLRStrongName::StrongNameGetPublicKey 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameGetPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameGetPublicKey
helpviewer_keywords:
- StrongNameGetPublicKey method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameGetPublicKey method [.NET Framework hosting]
ms.assetid: a31dcaa9-a404-4c1d-8cc7-081827c52935
topic_type:
- apiref
ms.openlocfilehash: cb96c7e17627205db0573e56fc8c2a29e7717434
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79181932"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="3a8ff-102">ICLRStrongName::StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="3a8ff-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="3a8ff-103">공개/개인 키 쌍에서 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="3a8ff-104">키 쌍은 CSP(암호화 서비스 공급자) 내에서 키 컨테이너 이름으로 또는 원시 바이트 컬렉션으로 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a8ff-105">구문</span><span class="sxs-lookup"><span data-stu-id="3a8ff-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a8ff-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3a8ff-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="3a8ff-107">【인】 공개/개인 키 쌍을 포함하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="3a8ff-108">null인 `pbKeyBlob` 경우 `szKeyContainer` CSP 내에서 유효한 컨테이너를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="3a8ff-109">이 경우 [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) 메서드는 컨테이너에 저장된 키 쌍에서 공개 키를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="3a8ff-110">null이 아닌 경우 `pbKeyBlob` 키 쌍은 키 이진 큰 개체(BLOB)에 포함되는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="3a8ff-111">키는 1024비트 Rivest-Shamir-Adleman(RSA) 서명 키여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="3a8ff-112">현재 다른 유형의 키는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="3a8ff-113">【인】 공용/개인 키 쌍에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="3a8ff-114">이 쌍은 Win32 `CryptExportKey` 함수에서 만든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="3a8ff-115">null인 경우 `pbKeyBlob` 지정한 `szKeyContainer` 키 컨테이너는 키 쌍을 포함하는 것으로 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="3a8ff-116">【인】 의 크기(바이트)입니다. `pbKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="3a8ff-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="3a8ff-117">【아웃】 반환된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="3a8ff-118">매개 `ppbPublicKeyBlob` 변수는 공통 언어 런타임에 의해 할당되고 호출자에게 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="3a8ff-119">호출자는 [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용하여 메모리를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="3a8ff-120">【아웃】 반환된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a8ff-121">Return Value</span><span class="sxs-lookup"><span data-stu-id="3a8ff-121">Return Value</span></span>  
 <span data-ttu-id="3a8ff-122">`S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="3a8ff-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3a8ff-123">설명</span><span class="sxs-lookup"><span data-stu-id="3a8ff-123">Remarks</span></span>  
 <span data-ttu-id="3a8ff-124">공개 키는 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a8ff-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3a8ff-125">Requirements</span></span>  
 <span data-ttu-id="3a8ff-126">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3a8ff-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a8ff-127">**헤더:** 메타호스트</span><span class="sxs-lookup"><span data-stu-id="3a8ff-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3a8ff-128">**라이브러리:** MSCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="3a8ff-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a8ff-129">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a8ff-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a8ff-130">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3a8ff-130">See also</span></span>

- [<span data-ttu-id="3a8ff-131">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="3a8ff-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="3a8ff-132">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="3a8ff-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="3a8ff-133">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3a8ff-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
