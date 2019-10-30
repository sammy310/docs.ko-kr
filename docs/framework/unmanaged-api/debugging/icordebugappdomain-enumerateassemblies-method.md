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
ms.openlocfilehash: 573b08fcf2ce0fa5ce3187df6ae6a1c2cc385f52
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134003"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="3d04d-102">ICorDebugAppDomain::EnumerateAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="3d04d-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="3d04d-103">응용 프로그램 도메인의 어셈블리에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="3d04d-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d04d-104">구문</span><span class="sxs-lookup"><span data-stu-id="3d04d-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3d04d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3d04d-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="3d04d-106">제한이 응용 프로그램 도메인에 있는 어셈블리의 열거자 인 ICorDebugAssemblyEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="3d04d-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3d04d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3d04d-107">Requirements</span></span>  
 <span data-ttu-id="3d04d-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d04d-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d04d-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="3d04d-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="3d04d-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3d04d-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3d04d-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d04d-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
