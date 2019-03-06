---
title: ICLRStrongName::StrongNameTokenFromAssemblyEx 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssemblyEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssemblyEx
helpviewer_keywords:
- StrongNameTokenFromAssemblyEx method, ICLRStrongName interface [.NET Framework hosting]
- ICLRStrongName::StrongNameTokenFromAssemblyEx method [.NET Framework hosting]
ms.assetid: 648ea90e-5e60-40a0-a56a-3e61bf2fba7c
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5abc09f06bfd2aec270e5ef91fd4778d6aa9a3b4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57487371"
---
# <a name="iclrstrongnamestrongnametokenfromassemblyex-method"></a><span data-ttu-id="c3deb-102">ICLRStrongName::StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="c3deb-102">ICLRStrongName::StrongNameTokenFromAssemblyEx Method</span></span>
<span data-ttu-id="c3deb-103">지정 된 어셈블리 파일에서 강력한 이름 토큰을 만들고 공개 키 토큰이 나타내는 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-103">Creates a strong name token from the specified assembly file, and returns the public key that the token represents.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c3deb-104">구문</span><span class="sxs-lookup"><span data-stu-id="c3deb-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssemblyEx (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken,  
    [out] BYTE      **ppbPublicKeyBlob,  
    [out] ULONG     *pcbPublicKeyBlob  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c3deb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c3deb-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c3deb-106">[in] 어셈블리의 pe (이식 가능) 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c3deb-107">[out] 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c3deb-108">[out] 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
 `ppbPublicKeyBlob`  
 <span data-ttu-id="c3deb-109">[out] 반환 된 공개 키입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-109">[out] The returned public key.</span></span>  
  
 `pcbPublicKeyBlob`  
 <span data-ttu-id="c3deb-110">[out] 공개 키의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-110">[out] The size, in bytes, of the public key.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c3deb-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="c3deb-111">Return Value</span></span>  
 <span data-ttu-id="c3deb-112">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="c3deb-112">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c3deb-113">설명</span><span class="sxs-lookup"><span data-stu-id="c3deb-113">Remarks</span></span>  
 <span data-ttu-id="c3deb-114">강력한 이름 토큰은 공개 키의 축약 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-114">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="c3deb-115">토큰은 어셈블리 서명에 사용 된 공개 키에서 생성 되는 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-115">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="c3deb-116">토큰에는 어셈블리에 대 한 강력한 이름의 일부인 되며 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-116">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="c3deb-117">키가 검색 후 토큰이 만들어지기 호출 해야 합니다 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 할당 된 메모리를 해제 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c3deb-117">After the key is retrieved and the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c3deb-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c3deb-118">Requirements</span></span>  
 <span data-ttu-id="c3deb-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c3deb-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c3deb-120">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c3deb-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c3deb-121">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c3deb-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c3deb-122">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c3deb-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c3deb-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="c3deb-123">See also</span></span>
- [<span data-ttu-id="c3deb-124">StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="c3deb-124">StrongNameTokenFromAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassembly-method.md)
- [<span data-ttu-id="c3deb-125">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c3deb-125">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
