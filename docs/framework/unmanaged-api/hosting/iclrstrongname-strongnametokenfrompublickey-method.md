---
title: ICLRStrongName::StrongNameTokenFromPublicKey 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromPublicKey
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromPublicKey method [.NET Framework hosting]
- StrongNameTokenFromPublicKey method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 7962ce88-7e86-4a6f-8298-621b01ffc3c2
topic_type:
- apiref
ms.openlocfilehash: 919c1321f18ca163481d27fa204c78f38af1e456
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176320"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="aec7d-102">ICLRStrongName::StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="aec7d-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="aec7d-103">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="aec7d-104">강력한 이름 토큰은 공개 키의 단축된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aec7d-105">구문</span><span class="sxs-lookup"><span data-stu-id="aec7d-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aec7d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aec7d-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="aec7d-107">【인】 강력한 이름 서명을 생성하는 데 사용되는 키 쌍의 공용 부분을 포함하는 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 형식의 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="aec7d-108">【인】 의 크기(바이트)입니다. `pbPublicKeyBlob`</span><span class="sxs-lookup"><span data-stu-id="aec7d-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="aec7d-109">【아웃】 에 전달된 키에 해당하는 `pbPublicKeyBlob`강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="aec7d-110">공통 언어 런타임은 토큰을 반환할 메모리를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="aec7d-111">호출자는 [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용하여 이 메모리를 해제해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="aec7d-112">【아웃】 반환된 강력한 이름 토큰의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="aec7d-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="aec7d-113">Return Value</span></span>  
 <span data-ttu-id="aec7d-114">`S_OK`메서드가 성공적으로 완료된 경우 그렇지 않으면 실패를 나타내는 HRESULT 값입니다(목록의 [공통 HRESULT 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="aec7d-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aec7d-115">설명</span><span class="sxs-lookup"><span data-stu-id="aec7d-115">Remarks</span></span>  
 <span data-ttu-id="aec7d-116">강력한 이름 토큰은 메타데이터에 키 정보를 저장할 때 공간을 절약하는 데 사용되는 공개 키의 단축된 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="aec7d-117">특히 강력한 이름 토큰은 종속 어셈블리를 참조하기 위해 어셈블리 참조에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aec7d-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aec7d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aec7d-118">Requirements</span></span>  
 <span data-ttu-id="aec7d-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aec7d-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aec7d-120">**헤더:** 메타호스트</span><span class="sxs-lookup"><span data-stu-id="aec7d-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="aec7d-121">**라이브러리:** mscoree.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="aec7d-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="aec7d-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aec7d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec7d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aec7d-123">See also</span></span>

- [<span data-ttu-id="aec7d-124">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="aec7d-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="aec7d-125">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="aec7d-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="aec7d-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aec7d-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
