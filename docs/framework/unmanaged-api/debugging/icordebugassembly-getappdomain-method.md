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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a9ba09b80d7118b0ccd9b1647011a7fc7cd74e22
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61645593"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="38ac8-102">ICorDebugAssembly::GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="38ac8-102">ICorDebugAssembly::GetAppDomain Method</span></span>
<span data-ttu-id="38ac8-103">이 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugAssembly` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="38ac8-103">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38ac8-104">구문</span><span class="sxs-lookup"><span data-stu-id="38ac8-104">Syntax</span></span>  
  
```  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="38ac8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38ac8-105">Parameters</span></span>  
 `ppAppDomain`  
 <span data-ttu-id="38ac8-106">[out] 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38ac8-106">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38ac8-107">설명</span><span class="sxs-lookup"><span data-stu-id="38ac8-107">Remarks</span></span>  
 <span data-ttu-id="38ac8-108">이 어셈블리가 시스템 어셈블리인 경우 `GetAppDomain` null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38ac8-108">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38ac8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38ac8-109">Requirements</span></span>  
 <span data-ttu-id="38ac8-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="38ac8-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38ac8-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="38ac8-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="38ac8-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="38ac8-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="38ac8-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38ac8-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
