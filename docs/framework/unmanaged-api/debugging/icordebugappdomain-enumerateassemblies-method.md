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
ms.openlocfilehash: 6bacd93baae3f0c0b70c4b910e8130551b4f3e48
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67738057"
---
# <a name="icordebugappdomainenumerateassemblies-method"></a><span data-ttu-id="f60e1-102">ICorDebugAppDomain::EnumerateAssemblies 메서드</span><span class="sxs-lookup"><span data-stu-id="f60e1-102">ICorDebugAppDomain::EnumerateAssemblies Method</span></span>
<span data-ttu-id="f60e1-103">응용 프로그램 도메인에서 어셈블리에 대 한 열거자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f60e1-103">Gets an enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f60e1-104">구문</span><span class="sxs-lookup"><span data-stu-id="f60e1-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateAssemblies (  
    [out] ICorDebugAssemblyEnum  **ppAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f60e1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f60e1-105">Parameters</span></span>  
 `ppAssemblies`  
 <span data-ttu-id="f60e1-106">[out] 응용 프로그램 도메인의 어셈블리에 대 한 열거자는 ICorDebugAssemblyEnum 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f60e1-106">[out] A pointer to the address of an ICorDebugAssemblyEnum object that is the enumerator for the assemblies in the application domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f60e1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f60e1-107">Requirements</span></span>  
 <span data-ttu-id="f60e1-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f60e1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f60e1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f60e1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f60e1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f60e1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f60e1-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f60e1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
