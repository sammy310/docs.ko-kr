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
ms.openlocfilehash: 01c7cb2e4359a477c26f995602dbf29668e567c0
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73131018"
---
# <a name="icordebugilframegetargument-method"></a><span data-ttu-id="33622-102">ICorDebugILFrame::GetArgument 메서드</span><span class="sxs-lookup"><span data-stu-id="33622-102">ICorDebugILFrame::GetArgument Method</span></span>
<span data-ttu-id="33622-103">이 MSIL (Microsoft 중간 언어) 스택 프레임에서 지정 된 인수의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="33622-103">Gets the value of the specified argument in this Microsoft intermediate language (MSIL) stack frame.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="33622-104">구문</span><span class="sxs-lookup"><span data-stu-id="33622-104">Syntax</span></span>  
  
```cpp  
HRESULT GetArgument (  
    [in] DWORD                  dwIndex,  
    [out] ICorDebugValue        **ppValue  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="33622-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="33622-105">Parameters</span></span>  
 `dwIndex`  
 <span data-ttu-id="33622-106">진행 이 MSIL 스택 프레임에 있는 인수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="33622-106">[in] The index of the argument in this MSIL stack frame.</span></span>  
  
 `ppValue`  
 <span data-ttu-id="33622-107">제한이 검색 된 값을 나타내는 ICorDebugValue 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="33622-107">[out] A pointer to the address of an ICorDebugValue object that represents the retrieved value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="33622-108">주의</span><span class="sxs-lookup"><span data-stu-id="33622-108">Remarks</span></span>  
 <span data-ttu-id="33622-109">`GetArgument` 메서드는 MSIL 스택 프레임 또는 JIT (just-in-time) 컴파일된 프레임에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="33622-109">The `GetArgument` method can be used either in an MSIL stack frame or in a just-in-time (JIT) compiled frame.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="33622-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="33622-110">Requirements</span></span>  
 <span data-ttu-id="33622-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="33622-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="33622-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="33622-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="33622-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="33622-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="33622-114">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="33622-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>
