---
title: ICorDebugAppDomain::EnumerateAssemblies 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAppDomain.EnumerateAssemblies
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAppDomain::EnumerateAssemblies
helpviewer_keywords:
- ICorDebugAppDomain::EnumerateAssemblies method [.NET Framework debugging]
- EnumerateAssemblies method [.NET Framework debugging]
ms.assetid: 7add64f9-19a8-46a9-be62-905d5e7d1bd8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 6ce95daaee3c74ac57b107ab8bcb23d41e42cabb
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466650"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="6b2f8-102">ICorDebugAppDomain::EnumerateAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="6b2f8-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="6b2f8-103">응용 프로그램 도메인에서 어셈블리에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f8-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b2f8-104">구문</span><span class="sxs-lookup"><span data-stu-id="6b2f8-104">Syntax</span></span>  
  
```  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b2f8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6b2f8-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="6b2f8-106">[out] 응용 프로그램 도메인의 어셈블리에 대 한 열거자는 ICorDebugAssemblyEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6b2f8-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6b2f8-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6b2f8-107">Requirements</span></span>  
 <span data-ttu-id="6b2f8-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6b2f8-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b2f8-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6b2f8-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6b2f8-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6b2f8-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6b2f8-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b2f8-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
