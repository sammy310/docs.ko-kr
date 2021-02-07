---
description: '자세히 알아보기: ICorDebugProcess5:: GetArrayLayout 메서드'
title: ICorDebugProcess5::GetArrayLayout 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugProcess5.GetArrayLayout
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugProcess5::GetArrayLayout
helpviewer_keywords:
- ICorDebugProcess5::GetArrayLayout method [.NET Framework debugging]
- GetArrayLayout method, ICorDebugProcess5 interface [.NET Framework debugging]
ms.assetid: 9a7393b9-9735-43c6-8616-afb103c432fd
topic_type:
- apiref
ms.openlocfilehash: c82b296da3a367f5307240225a560af67a56c866
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99746401"
---
# <a name="icordebugprocess5getarraylayout-method"></a><span data-ttu-id="0920d-103">ICorDebugProcess5::GetArrayLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="0920d-103">ICorDebugProcess5::GetArrayLayout Method</span></span>

<span data-ttu-id="0920d-104">배열 형식의 레이아웃에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0920d-104">Provides information about the layout of array types.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0920d-105">구문</span><span class="sxs-lookup"><span data-stu-id="0920d-105">Syntax</span></span>  
  
```cpp  
HRESULT GetArrayLayout(    [in] COR_TYPEID id,     [out] COR_ARRAY_LAYOUT *pLayout);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0920d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0920d-106">Parameters</span></span>  

 `id`  
 <span data-ttu-id="0920d-107">진행 레이아웃이 필요한 배열을 지정 하는 [COR_TYPEID](cor-typeid-structure.md) 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="0920d-107">[in] A [COR_TYPEID](cor-typeid-structure.md) token that specifies the array whose layout is desired.</span></span>  
  
 `pLayout`  
 <span data-ttu-id="0920d-108">제한이 메모리의 배열 레이아웃에 대 한 정보를 포함 하는 [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) 구조체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0920d-108">[out] A pointer to a [COR_ARRAY_LAYOUT](cor-array-layout-structure.md) structure that contains information about the layout of the array in memory.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0920d-109">설명</span><span class="sxs-lookup"><span data-stu-id="0920d-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0920d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0920d-110">Requirements</span></span>  

 <span data-ttu-id="0920d-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0920d-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0920d-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0920d-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0920d-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0920d-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0920d-114">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0920d-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0920d-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0920d-115">See also</span></span>

- [<span data-ttu-id="0920d-116">ICorDebugProcess5 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0920d-116">ICorDebugProcess5 Interface</span></span>](icordebugprocess5-interface.md)
- [<span data-ttu-id="0920d-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0920d-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
