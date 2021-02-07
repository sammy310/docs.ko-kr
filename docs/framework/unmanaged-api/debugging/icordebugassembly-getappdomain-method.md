---
description: '자세히 알아보기: ICorDebugAssembly:: GetAppDomain 메서드'
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
ms.openlocfilehash: f67b2a211b080843e2bd7b8820a5bf54dae638e3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712105"
---
# <a name="icordebugassemblygetappdomain-method"></a><span data-ttu-id="5ab9f-103">ICorDebugAssembly::GetAppDomain 메서드</span><span class="sxs-lookup"><span data-stu-id="5ab9f-103">ICorDebugAssembly::GetAppDomain Method</span></span>

<span data-ttu-id="5ab9f-104">이 인스턴스를 포함 하는 응용 프로그램 도메인에 대 한 인터페이스 포인터를 가져옵니다 `ICorDebugAssembly` .</span><span class="sxs-lookup"><span data-stu-id="5ab9f-104">Gets an interface pointer to the application domain that contains this `ICorDebugAssembly` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ab9f-105">구문</span><span class="sxs-lookup"><span data-stu-id="5ab9f-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAppDomain (  
    [out] ICorDebugAppDomain  **ppAppDomain  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ab9f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ab9f-106">Parameters</span></span>  

 `ppAppDomain`  
 <span data-ttu-id="5ab9f-107">제한이 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5ab9f-107">[out] A pointer to the address of an ICorDebugAppDomain interface that represents the application domain.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ab9f-108">설명</span><span class="sxs-lookup"><span data-stu-id="5ab9f-108">Remarks</span></span>  

 <span data-ttu-id="5ab9f-109">이 어셈블리가 시스템 어셈블리인 경우 `GetAppDomain` null을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="5ab9f-109">If this assembly is the system assembly, `GetAppDomain` returns null.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ab9f-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5ab9f-110">Requirements</span></span>  

 <span data-ttu-id="5ab9f-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5ab9f-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ab9f-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5ab9f-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5ab9f-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5ab9f-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5ab9f-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ab9f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
