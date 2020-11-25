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
ms.openlocfilehash: 5bd314b2b63474d2a1d159f74564e2d4ca13aef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725549"
---
# <a name="iclrstrongnamestrongnamegetpublickey-method"></a><span data-ttu-id="87a6d-102">ICLRStrongName::StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="87a6d-102">ICLRStrongName::StrongNameGetPublicKey Method</span></span>

<span data-ttu-id="87a6d-103">공개/개인 키 쌍에서 공개 키를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-103">Gets the public key from a public/private key pair.</span></span> <span data-ttu-id="87a6d-104">키 쌍은 CSP (암호화 서비스 공급자) 내에서 키 컨테이너 이름으로 제공 되거나 원시 바이트 컬렉션으로 제공 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-104">The key pair can be supplied either as a key container name within a cryptographic service provider (CSP) or as a raw collection of bytes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="87a6d-105">구문</span><span class="sxs-lookup"><span data-stu-id="87a6d-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameGetPublicKey (
    [in]  LPCWSTR   szKeyContainer,  
    [in]  BYTE      *pbKeyBlob,  
    [in]  ULONG     cbKeyBlob,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="87a6d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="87a6d-106">Parameters</span></span>  

 `szKeyContainer`  
 <span data-ttu-id="87a6d-107">진행 공개/개인 키 쌍을 포함 하는 키 컨테이너의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-107">[in] The name of the key container that contains the public/private key pair.</span></span> <span data-ttu-id="87a6d-108">가 null 인 경우는 `pbKeyBlob` `szKeyContainer` CSP 내에서 유효한 컨테이너를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-108">If `pbKeyBlob` is null, `szKeyContainer` must specify a valid container within the CSP.</span></span> <span data-ttu-id="87a6d-109">이 경우 [ICLRStrongName:: StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) 메서드는 컨테이너에 저장 된 키 쌍에서 공개 키를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-109">In this case, the [ICLRStrongName::StrongNameGetPublicKey](iclrstrongname-strongnamegetpublickey-method.md) method extracts the public key from the key pair stored in the container.</span></span>  
  
 <span data-ttu-id="87a6d-110">`pbKeyBlob`가 null이 아닌 경우 키 쌍은 키 BLOB (binary large object)에 포함 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-110">If `pbKeyBlob` is not null, the key pair is assumed to be contained in the key binary large object (BLOB).</span></span>  
  
 <span data-ttu-id="87a6d-111">키는 1024 비트 RSA (Rivest Rivest-shamir-adleman Rivest-shamir-adleman) 서명 키 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-111">The keys must be 1024-bit Rivest-Shamir-Adleman (RSA) signing keys.</span></span> <span data-ttu-id="87a6d-112">지금은 다른 유형의 키를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-112">No other types of keys are supported at this time.</span></span>  
  
 `pbKeyBlob`  
 <span data-ttu-id="87a6d-113">진행 공개/개인 키 쌍에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-113">[in] A pointer to the public/private key pair.</span></span> <span data-ttu-id="87a6d-114">이 쌍은 Win32 함수에서 만든 형식입니다 `CryptExportKey` .</span><span class="sxs-lookup"><span data-stu-id="87a6d-114">This pair is in the format created by the Win32 `CryptExportKey` function.</span></span> <span data-ttu-id="87a6d-115">가 null 인 경우에 `pbKeyBlob` 지정 된 키 컨테이너는 `szKeyContainer` 키 쌍을 포함 하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-115">If `pbKeyBlob` is null, the key container specified by `szKeyContainer` is assumed to contain the key pair.</span></span>  
  
 `cbKeyBlob`  
 <span data-ttu-id="87a6d-116">진행 의 크기 (바이트)입니다 `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="87a6d-116">[in] The size, in bytes, of `pbKeyBlob`.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="87a6d-117">제한이 반환 된 공개 키 BLOB입니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-117">[out] The returned public key BLOB.</span></span> <span data-ttu-id="87a6d-118">`ppbPublicKeyBlob`매개 변수는 공용 언어 런타임에 의해 할당 되 고 호출자에 게 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-118">The `ppbPublicKeyBlob` parameter is allocated by the common language runtime and returned to the caller.</span></span> <span data-ttu-id="87a6d-119">호출자는 [ICLRStrongName:: StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 하 여 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-119">The caller must free the memory by using the [ICLRStrongName::StrongNameFreeBuffer](iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="87a6d-120">제한이 반환 된 공개 키 BLOB의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-120">[out] The size of the returned public key BLOB.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="87a6d-121">반환 값</span><span class="sxs-lookup"><span data-stu-id="87a6d-121">Return Value</span></span>  

 <span data-ttu-id="87a6d-122">`S_OK` 메서드가 성공적으로 완료 되었으면이 고, 그렇지 않으면입니다. 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="87a6d-122">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="87a6d-123">설명</span><span class="sxs-lookup"><span data-stu-id="87a6d-123">Remarks</span></span>  

 <span data-ttu-id="87a6d-124">공개 키가 [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) 구조에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-124">The public key is contained in a [PublicKeyBlob](../strong-naming/publickeyblob-structure.md) structure.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="87a6d-125">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87a6d-125">Requirements</span></span>  

 <span data-ttu-id="87a6d-126">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87a6d-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87a6d-127">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="87a6d-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="87a6d-128">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87a6d-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87a6d-129">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87a6d-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87a6d-130">참조</span><span class="sxs-lookup"><span data-stu-id="87a6d-130">See also</span></span>

- [<span data-ttu-id="87a6d-131">StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="87a6d-131">StrongNameTokenFromPublicKey Method</span></span>](iclrstrongname-strongnametokenfrompublickey-method.md)
- [<span data-ttu-id="87a6d-132">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="87a6d-132">PublicKeyBlob Structure</span></span>](../strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="87a6d-133">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87a6d-133">ICLRStrongName Interface</span></span>](iclrstrongname-interface.md)
