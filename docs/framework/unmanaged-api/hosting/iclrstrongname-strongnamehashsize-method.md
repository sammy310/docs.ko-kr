---
title: ICLRStrongName::StrongNameHashSize 메서드
ms.date: 03/30/2017
api_name:
- ICLRStrongName.StrongNameHashSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRStrongName::StrongNameHashSize
helpviewer_keywords:
- ICLRStrongName::StrongNameHashSize method [.NET Framework hosting]
- StrongNameHashSize method, ICLRStrongName interface [.NET Framework hosting]
ms.assetid: 4a05ee56-08e4-4f3a-86a9-9b52083d5c0f
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 91b84a980e8a670b8e8b2970cfc96ddd6f4c33b5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61704078"
---
# <a name="iclrstrongnamestrongnamehashsize-method"></a><span data-ttu-id="01b77-102">ICLRStrongName::StrongNameHashSize 메서드</span><span class="sxs-lookup"><span data-stu-id="01b77-102">ICLRStrongName::StrongNameHashSize Method</span></span>
<span data-ttu-id="01b77-103">지정된 해시 알고리즘을 사용하여 해시에 필요한 버퍼 크기를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="01b77-103">Gets the buffer size required for a hash, using the specified hash algorithm.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01b77-104">구문</span><span class="sxs-lookup"><span data-stu-id="01b77-104">Syntax</span></span>  
  
```  
HRESULT StrongNameHashSize (  
    [in]  ULONG   ulHashAlg,  
    [out] DWORD   *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01b77-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01b77-105">Parameters</span></span>  
 `ulHashAlg`  
 <span data-ttu-id="01b77-106">[in] 버퍼 크기를 계산 하는 데 사용 된 해시 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="01b77-106">[in] The hash algorithm used to compute the buffer size.</span></span>  
  
 `pcbSize`  
 <span data-ttu-id="01b77-107">[out] 반환 된 버퍼 크기 (바이트)에서입니다.</span><span class="sxs-lookup"><span data-stu-id="01b77-107">[out] The returned buffer size, in bytes.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01b77-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="01b77-108">Return Value</span></span>  
 <span data-ttu-id="01b77-109">`S_OK` 메서드가 성공적으로 완료 하는 경우 그렇지 않으면 실패를 나타내는 HRESULT 값을 (참조 [일반적인 HRESULT 값](https://go.microsoft.com/fwlink/?LinkId=213878) 목록에 대 한).</span><span class="sxs-lookup"><span data-stu-id="01b77-109">`S_OK` if the method completed successfully; otherwise, an HRESULT value that indicates failure (see [Common HRESULT Values](https://go.microsoft.com/fwlink/?LinkId=213878) for a list).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01b77-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01b77-110">Requirements</span></span>  
 <span data-ttu-id="01b77-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="01b77-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01b77-112">**헤더:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="01b77-112">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="01b77-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="01b77-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="01b77-114">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="01b77-114">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01b77-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="01b77-115">See also</span></span>

- [<span data-ttu-id="01b77-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="01b77-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
