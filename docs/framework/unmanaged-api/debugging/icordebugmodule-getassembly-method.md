---
description: '자세히 알아보기: ICorDebugModule:: GetAssembly 메서드'
title: ICorDebugModule::GetAssembly 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetAssembly
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetAssembly
helpviewer_keywords:
- ICorDebugModule::GetAssembly method [.NET Framework debugging]
- GetAssembly method [.NET Framework debugging]
ms.assetid: 989762c4-3d15-4485-b8ee-69e0fa8ec895
topic_type:
- apiref
ms.openlocfilehash: 88bda923cd4c3ebfa5da6b3343e1cead4cebbad9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99722618"
---
# <a name="icordebugmodulegetassembly-method"></a><span data-ttu-id="bd144-103">ICorDebugModule::GetAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="bd144-103">ICorDebugModule::GetAssembly Method</span></span>

<span data-ttu-id="bd144-104">이 모듈에 대 한 포함 어셈블리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="bd144-104">Gets the containing assembly for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd144-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd144-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssembly(  
    [out] ICorDebugAssembly **ppAssembly  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bd144-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bd144-106">Parameters</span></span>  

 `ppAssembly`  
 <span data-ttu-id="bd144-107">제한이 이 모듈을 포함 하는 어셈블리를 나타내는 ICorDebugAssembly 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bd144-107">[out] A pointer to an ICorDebugAssembly object that represents the assembly containing this module.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bd144-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd144-108">Requirements</span></span>  

 <span data-ttu-id="bd144-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bd144-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bd144-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bd144-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bd144-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bd144-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bd144-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bd144-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
