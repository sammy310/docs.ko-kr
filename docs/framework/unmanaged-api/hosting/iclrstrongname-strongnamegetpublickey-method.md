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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e66835ec1cdf1327a39223b6cdb187ec47cd7e3d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57476310"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="e8c49-102">ICLRStrongName::StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="e8c49-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>
<span data-ttu-id="e8c49-103">공개/개인 키 쌍에서 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="e8c49-104">암호화 서비스 공급자 (CSP) 내에서 키 컨테이너 이름으로 또는 원시 바이트 컬렉션으로 키 쌍을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8c49-105">구문</span><span class="sxs-lookup"><span data-stu-id="e8c49-105">Syntax</span></span>  
  
```  
HRESULT StrongNameGetPublicKey (   
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8c49-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e8c49-106">Parameters</span></span>  
 `szKeyContainer`  
 <span data-ttu-id="e8c49-107">[in] 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="e8c49-108">하는 경우 `pbKeyBlob` 이 null 이면 `szKeyContainer` CSP 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="e8c49-109">이 경우에 [iclrstrongname:: Strongnamegetpublickey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) 메서드 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="e8c49-110">경우 `pbKeyBlob` null이 아니면 키 쌍 가정 키 binary large object (BLOB)에 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="e8c49-111">키에는 1024 비트 adleman의 Rivest-Shamir (RSA) 키를 서명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="e8c49-112">다른 종류의 키이 이번에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="e8c49-113">[in] 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="e8c49-114">이 쌍이 win32 만들어진 형식을 `CryptExportKey` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="e8c49-115">하는 경우 `pbKeyBlob` 가 null 이면 지정 된 키 컨테이너 `szKeyContainer` 키 쌍을 포함 하도록 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="e8c49-116">[in] 크기 (바이트)의 `pbKeyBlob`합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="e8c49-117">[out] 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="e8c49-118">`ppbPublicKeyBlob` 매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="e8c49-119">호출자에 게 사용 하 여 메모리를 해제 해야 합니다 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드.</span><span class="sxs-lookup"><span data-stu-id="e8c49-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="e8c49-120">[out] 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e8c49-121">반환 값</span><span class="sxs-lookup"><span data-stu-id="e8c49-121">Return Value</span></span>  
 <span data-ttu-id="e8c49-122">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="e8c49-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e8c49-123">설명</span><span class="sxs-lookup"><span data-stu-id="e8c49-123">Remarks</span></span>  
 <span data-ttu-id="e8c49-124">공개 키에 포함 된 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="e8c49-124">The public key is contained in a [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8c49-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e8c49-125">Requirements</span></span>  
 <span data-ttu-id="e8c49-126">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8c49-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8c49-127">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e8c49-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e8c49-128">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="e8c49-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e8c49-129">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e8c49-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8c49-130">참고자료</span><span class="sxs-lookup"><span data-stu-id="e8c49-130">See also</span></span>
- [<span data-ttu-id="e8c49-131">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="e8c49-131">StrongNameTokenFromPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="e8c49-132">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="e8c49-132">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="e8c49-133">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e8c49-133">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
