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
ms.openlocfilehash: 13c1c505d939c1048eebef3d1d6b2abe493d319e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937412"
---
# <a name="iclrstrongnamestrongnametokenfrompublickey-method"></a><span data-ttu-id="bfede-102">ICLRStrongName::StrongNameTokenFromPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="bfede-102">ICLRStrongName::StrongNameTokenFromPublicKey Method</span></span>
<span data-ttu-id="bfede-103">공개 키를 나타내는 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-103">Gets a token that represents a public key.</span></span> <span data-ttu-id="bfede-104">강력한 이름 토큰은 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-104">A strong name token is the shortened form of a public key.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bfede-105">구문</span><span class="sxs-lookup"><span data-stu-id="bfede-105">Syntax</span></span>  
  
```cpp  
HRESULT StrongNameTokenFromPublicKey (   
    [in]  BYTE    *pbPublicKeyBlob,  
    [in]  ULONG   cbPublicKeyBlob,  
    [out] BYTE    **ppbStrongNameToken,  
    [out] ULONG   *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bfede-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bfede-106">Parameters</span></span>  
 `pbPublicKeyBlob`  
 <span data-ttu-id="bfede-107">진행 강력한 이름 서명을 생성 하는 데 사용 되는 키 쌍의 공개 부분을 포함 하는 [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) 형식의 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-107">[in] A structure of type [PublicKeyBlob](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md) that contains the public portion of the key pair used to generate the strong name signature.</span></span>  
  
 `cbPublicKeyBlob`  
 <span data-ttu-id="bfede-108">진행 `pbPublicKeyBlob`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-108">[in] The size, in bytes, of `pbPublicKeyBlob`.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="bfede-109">제한이 `pbPublicKeyBlob`전달 된 키에 해당 하는 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-109">[out] The strong name token corresponding to the key passed in `pbPublicKeyBlob`.</span></span> <span data-ttu-id="bfede-110">공용 언어 런타임은 토큰을 반환할 메모리를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-110">The common language runtime allocates the memory in which to return the token.</span></span> <span data-ttu-id="bfede-111">호출자는 [ICLRStrongName:: StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드를 사용 하 여이 메모리를 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-111">The caller must free this memory by using the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="bfede-112">제한이 반환 된 강력한 이름 토큰의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-112">[out] The size, in bytes, of the returned strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="bfede-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="bfede-113">Return Value</span></span>  
 <span data-ttu-id="bfede-114">메서드가 성공적으로 완료 되 면 `S_OK` 하 고, 그렇지 않으면 오류를 나타내는 HRESULT 값입니다 (목록의 [일반적인 Hresult 값](/windows/win32/seccrypto/common-hresult-values) 참조).</span><span class="sxs-lookup"><span data-stu-id="bfede-114">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](/windows/win32/seccrypto/common-hresult-values) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bfede-115">주의</span><span class="sxs-lookup"><span data-stu-id="bfede-115">Remarks</span></span>  
 <span data-ttu-id="bfede-116">강력한 이름 토큰은 키 정보를 메타 데이터에 저장할 때 공간을 절약 하는 데 사용 되는 공개 키의 축약 된 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-116">A strong name token is the shortened form of a public key that is used to save space when storing key information in metadata.</span></span> <span data-ttu-id="bfede-117">특히 강력한 이름 토큰은 어셈블리 참조에서 종속 어셈블리를 참조 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-117">Specifically, strong name tokens are used in assembly references to refer to the dependent assembly.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bfede-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bfede-118">Requirements</span></span>  
 <span data-ttu-id="bfede-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bfede-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bfede-120">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="bfede-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="bfede-121">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfede-121">**Library:** Included as a resource in mscoree.dll</span></span>  
  
 <span data-ttu-id="bfede-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bfede-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bfede-123">참조</span><span class="sxs-lookup"><span data-stu-id="bfede-123">See also</span></span>

- [<span data-ttu-id="bfede-124">StrongNameGetPublicKey 메서드</span><span class="sxs-lookup"><span data-stu-id="bfede-124">StrongNameGetPublicKey Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamegetpublickey-method.md)
- [<span data-ttu-id="bfede-125">PublicKeyBlob 구조체</span><span class="sxs-lookup"><span data-stu-id="bfede-125">PublicKeyBlob Structure</span></span>](../../../../docs/framework/unmanaged-api/strong-naming/publickeyblob-structure.md)
- [<span data-ttu-id="bfede-126">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bfede-126">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
