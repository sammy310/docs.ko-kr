---
title: ICorDebugAssembly::GetAppDomain 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugAssembly.GetAppDomain
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugAssembly::GetAppDomain
helpviewer_keywords:
- ICorDebugAssembly::GetAppDomain method [.NET Framework debugging]
- GetAppDomain method, ICorDebugAssembly interface [.NET Framework debugging]
ms.assetid: 14e18510-23ac-4cba-9f96-c86147a2df9d
topic_type:
- apiref
ms.openlocfilehash: 81936052c3fa2ad4fb77b503341b8b4873b80695
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82894940"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="95f52-102">ICorDebugAssembly::GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="95f52-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="95f52-103">이 `ICorDebugAssembly` 인스턴스를 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="95f52-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="95f52-104">구문</span><span class="sxs-lookup"><span data-stu-id="95f52-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="95f52-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="95f52-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="95f52-106">제한이 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="95f52-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="95f52-107">설명</span><span class="sxs-lookup"><span data-stu-id="95f52-107">Remarks</span></span>  
 <span data-ttu-id="95f52-108">이 어셈블리가 시스템 어셈블리인 경우 null을 `GetAppDomain` 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="95f52-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="95f52-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="95f52-109">Requirements</span></span>  
 <span data-ttu-id="95f52-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="95f52-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="95f52-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="95f52-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="95f52-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="95f52-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="95f52-113">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="95f52-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
