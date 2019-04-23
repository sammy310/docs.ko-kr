---
title: ICorDebugModule::IsInMemory 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.IsInMemory
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::IsInMemory
helpviewer_keywords:
- IsInMemory method [.NET Framework debugging]
- ICorDebugModule::IsInMemory method [.NET Framework debugging]
ms.assetid: 89940711-98e7-4aa6-bffc-5e39e91e1b7d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d79a8b0c3c56ffe2b8f57ec26f5942ee0d681194
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59187592"
---
# <a name="icordebugmoduleisinmemory-method"></a><span data-ttu-id="a3d36-102">ICorDebugModule::IsInMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="a3d36-102">ICorDebugModule::IsInMemory Method</span></span>
<span data-ttu-id="a3d36-103">메모리에만이 모듈 있는지 여부를 나타내는 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="a3d36-103">Gets a value that indicates whether this module exists only in memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3d36-104">구문</span><span class="sxs-lookup"><span data-stu-id="a3d36-104">Syntax</span></span>  
  
```  
HRESULT IsInMemory(  
    [out] BOOL *pInMemory  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a3d36-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a3d36-105">Parameters</span></span>  
 `pInMemory`  
 <span data-ttu-id="a3d36-106">[out] `true` 메모리에만이 모듈 존재 하는 경우이 고, 그렇지 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="a3d36-106">[out] `true` if this module exists only in memory; otherwise, `false`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a3d36-107">설명</span><span class="sxs-lookup"><span data-stu-id="a3d36-107">Remarks</span></span>  
 <span data-ttu-id="a3d36-108">CLR (공용 언어 런타임) 바이트의 원시 스트림에서 모듈의 로드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="a3d36-108">The common language runtime (CLR) supports the loading of modules from raw streams of bytes.</span></span> <span data-ttu-id="a3d36-109">이러한 모듈 이라고 *메모리 내 모듈* 하며 디스크에 존재 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a3d36-109">Such modules are called *in-memory modules* and do not exist on disk.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3d36-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a3d36-110">Requirements</span></span>  
 <span data-ttu-id="a3d36-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="a3d36-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3d36-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a3d36-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a3d36-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a3d36-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a3d36-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a3d36-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3d36-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="a3d36-115">See also</span></span>
