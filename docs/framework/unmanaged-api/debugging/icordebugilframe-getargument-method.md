---
title: ICorDebugILFrame::GetArgument 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugILFrame.GetArgument
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugILFrame::GetArgument
helpviewer_keywords:
- GetArgument method [.NET Framework debugging]
- ICorDebugILFrame::GetArgument method [.NET Framework debugging]
ms.assetid: 4e2fd423-f643-4c27-ba5f-41b5ebc3b416
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 46852ed8ac53c3a7720edff4833f3dc3cce42bbb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995529"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="ec90a-102">ICorDebugILFrame::GetArgument 메서드</span><span class="sxs-lookup"><span data-stu-id="ec90a-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="ec90a-103">이 Microsoft 중간 언어 (MSIL) 스택 프레임에서 지정 된 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ec90a-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec90a-104">구문</span><span class="sxs-lookup"><span data-stu-id="ec90a-104">Syntax</span></span>  
  
```  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec90a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec90a-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="ec90a-106">[in] 이 MSIL 스택 프레임에서 인수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="ec90a-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="ec90a-107">[out] 검색된 된 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ec90a-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec90a-108">설명</span><span class="sxs-lookup"><span data-stu-id="ec90a-108">Remarks</span></span>  
 <span data-ttu-id="ec90a-109">`GetArgument` 메서드는 MSIL 스택 프레임 또는 컴파일된 시간 (JIT)에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ec90a-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec90a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec90a-110">Requirements</span></span>  
 <span data-ttu-id="ec90a-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="ec90a-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec90a-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="ec90a-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="ec90a-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="ec90a-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="ec90a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec90a-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
