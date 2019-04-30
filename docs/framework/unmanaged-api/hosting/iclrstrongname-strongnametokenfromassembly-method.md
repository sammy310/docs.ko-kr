---
title: ICLRStrongName::StrongNameTokenFromAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameTokenFromAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly
helpviewer_keywords:
- ICLRStrongName::StrongNameTokenFromAssembly method [.NET Framework hosting]
- StrongNameTokenFromAssembly method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: fc725afb-b66b-4015-aa44-1c0d1304197f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8a2931c16e13d08c1e3e7d5b62e6583102a1b8cd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61984583"
---
# <a name="iclrstrongnamestrongnametokenfromassembly-method"></a><span data-ttu-id="c4e2a-102">ICLRStrongName::StrongNameTokenFromAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="c4e2a-102">ICLRStrongName::StrongNameTokenFromAssembly Method</span></span>
<span data-ttu-id="c4e2a-103">지정된 어셈블리 파일에서 강력한 이름 토큰을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-103">Creates a strong name token from the specified assembly file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c4e2a-104">구문</span><span class="sxs-lookup"><span data-stu-id="c4e2a-104">Syntax</span></span>  
  
```  
HRESULT StrongNameTokenFromAssembly (  
    [in]  LPCWSTR   wszFilePath,  
    [out] BYTE      **ppbStrongNameToken,  
    [out] ULONG     *pcbStrongNameToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c4e2a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c4e2a-105">Parameters</span></span>  
 `wszFilePath`  
 <span data-ttu-id="c4e2a-106">[in] 어셈블리의 pe (이식 가능) 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-106">[in] The path to the portable executable (PE) file for the assembly.</span></span>  
  
 `ppbStrongNameToken`  
 <span data-ttu-id="c4e2a-107">[out] 반환 된 강력한 이름 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-107">[out] The returned strong name token.</span></span>  
  
 `pcbStrongNameToken`  
 <span data-ttu-id="c4e2a-108">[out] 강력한 이름 토큰의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-108">[out] The size, in bytes, of the strong name token.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c4e2a-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="c4e2a-109">Return Value</span></span>  
 <span data-ttu-id="c4e2a-110">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="c4e2a-110">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c4e2a-111">설명</span><span class="sxs-lookup"><span data-stu-id="c4e2a-111">Remarks</span></span>  
 <span data-ttu-id="c4e2a-112">강력한 이름 토큰은 공개 키의 축약 형태입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-112">A strong name token is the shortened form of a public key.</span></span> <span data-ttu-id="c4e2a-113">토큰은 어셈블리 서명에 사용 된 공개 키에서 생성 되는 64 비트 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-113">The token is a 64-bit hash that is created from the public key used to sign the assembly.</span></span> <span data-ttu-id="c4e2a-114">토큰에는 어셈블리에 대 한 강력한 이름의 일부인 되며 어셈블리 메타 데이터에서 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-114">The token is a part of the strong name for the assembly, and can be read from the assembly metadata.</span></span>  
  
 <span data-ttu-id="c4e2a-115">토큰을 만든 후 호출 해야 합니다 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 할당 된 메모리를 해제 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-115">After the token is created, you should call the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method to release the allocated memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c4e2a-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c4e2a-116">Requirements</span></span>  
 <span data-ttu-id="c4e2a-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c4e2a-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c4e2a-118">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c4e2a-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c4e2a-119">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="c4e2a-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c4e2a-120">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c4e2a-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c4e2a-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="c4e2a-121">See also</span></span>

- [<span data-ttu-id="c4e2a-122">StrongNameTokenFromAssemblyEx 메서드</span><span class="sxs-lookup"><span data-stu-id="c4e2a-122">StrongNameTokenFromAssemblyEx Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnametokenfromassemblyex-method.md)
- [<span data-ttu-id="c4e2a-123">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c4e2a-123">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
