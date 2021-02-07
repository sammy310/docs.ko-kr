---
description: '자세히 알아보기: ICorDebugClass:: GetModule 메서드'
title: ICorDebugClass::GetModule 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugClass.GetModule
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugClass::GetModule
helpviewer_keywords:
- GetModule method, ICorDebugClass interface [.NET Framework debugging]
- ICorDebugClass::GetModule method [.NET Framework debugging]
ms.assetid: 87029cc4-e5e1-42d5-8b98-655bb7ece520
topic_type:
- apiref
ms.openlocfilehash: 338ea5aeede4a209f7a3e3ed685ae9bd84105890
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99711546"
---
# <a name="icordebugclassgetmodule-method"></a><span data-ttu-id="249c2-103">ICorDebugClass::GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="249c2-103">ICorDebugClass::GetModule Method</span></span>

<span data-ttu-id="249c2-104">이 클래스를 정의 하는 모듈을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="249c2-104">Gets the module that defines this class.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="249c2-105">구문</span><span class="sxs-lookup"><span data-stu-id="249c2-105">Syntax</span></span>  
  
```cpp  
HRESULT GetModule (  
    [out] ICorDebugModule    **pModule  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="249c2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="249c2-106">Parameters</span></span>  

 `pModule`  
 <span data-ttu-id="249c2-107">제한이 이 클래스가 정의 된 모듈을 나타내는 ICorDebugModule 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="249c2-107">[out] A pointer to the address of an ICorDebugModule object that represents the module in which this class is defined.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="249c2-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="249c2-108">Requirements</span></span>  

 <span data-ttu-id="249c2-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="249c2-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="249c2-110">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="249c2-110">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="249c2-111">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="249c2-111">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="249c2-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="249c2-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
