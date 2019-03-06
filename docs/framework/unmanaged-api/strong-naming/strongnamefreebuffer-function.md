---
title: StrongNameFreeBuffer 함수
ms.date: 03/30/2017
api_name:
- StrongNameFreeBuffer
api_location:
- mscoree.dll
- mscorsn.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameFreeBuffer
helpviewer_keywords:
- StrongNameFreeBuffer function [.NET Framework strong naming]
ms.assetid: eda21ecf-4734-4f92-aaba-9f34884385db
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: f308f6c1f977fad8fa102f30756f0e43c779cc8a
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57472059"
---
# <a name="strongnamefreebuffer-function"></a><span data-ttu-id="d63a6-102">StrongNameFreeBuffer 함수</span><span class="sxs-lookup"><span data-stu-id="d63a6-102">StrongNameFreeBuffer Function</span></span>
<span data-ttu-id="d63a6-103">[StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md) 또는 [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md)과 같은 강력한 이름 함수에 대한 이전 호출로 할당된 메모리를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a6-103">Frees memory that was allocated with a previous call to a strong name function such as [StrongNameGetPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnamegetpublickey-function.md), [StrongNameTokenFromPublicKey](../../../../docs/framework/unmanaged-api/strong-naming/strongnametokenfrompublickey-function.md), or [StrongNameSignatureGeneration](../../../../docs/framework/unmanaged-api/strong-naming/strongnamesignaturegeneration-function.md).</span></span>  
  
 <span data-ttu-id="d63a6-104">이 함수는 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d63a6-104">This function has been deprecated.</span></span> <span data-ttu-id="d63a6-105">사용 된 [iclrstrongname:: Strongnamefreebuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) 메서드 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="d63a6-105">Use the [ICLRStrongName::StrongNameFreeBuffer](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d63a6-106">구문</span><span class="sxs-lookup"><span data-stu-id="d63a6-106">Syntax</span></span>  
  
```  
VOID StrongNameFreeBuffer (   
   [in] BYTE   *pbMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d63a6-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d63a6-107">Parameters</span></span>  
 `pbMemory`  
 <span data-ttu-id="d63a6-108">[in] 사용 가능한 메모리에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d63a6-108">[in] A pointer to the memory to free.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d63a6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d63a6-109">Requirements</span></span>  
 <span data-ttu-id="d63a6-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d63a6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d63a6-111">**헤더:** StrongName.h</span><span class="sxs-lookup"><span data-stu-id="d63a6-111">**Header:** StrongName.h</span></span>  
  
 <span data-ttu-id="d63a6-112">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d63a6-112">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d63a6-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d63a6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d63a6-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="d63a6-114">See also</span></span>
- [<span data-ttu-id="d63a6-115">StrongNameFreeBuffer 메서드</span><span class="sxs-lookup"><span data-stu-id="d63a6-115">StrongNameFreeBuffer Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-strongnamefreebuffer-method.md)
- [<span data-ttu-id="d63a6-116">ICLRStrongName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d63a6-116">ICLRStrongName Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-interface.md)
