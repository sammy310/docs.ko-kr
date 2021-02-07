---
description: '자세히 알아보기: ICorDebugGuidToTypeEnum:: Next 메서드'
title: ICorDebugGuidToTypeEnum::Next 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugGuidToTypeEnum.Next
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugGuidToTypeEnum::Next
helpviewer_keywords:
- ICorDebugGuidToTypeEnum::Next method [.NET Framework debugging]
- Next method, ICorDebugGuidToTypeEnum interface [.NET Framework debugging]
ms.assetid: c9937666-8e18-484d-9fe0-b9ac95199530
topic_type:
- apiref
ms.openlocfilehash: 0ab05cc0689c76c0bb185205ea00c5ccebfcbe03
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661001"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="d81e4-103">ICorDebugGuidToTypeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="d81e4-103">ICorDebugGuidToTypeEnum::Next Method</span></span>

<span data-ttu-id="d81e4-104">Guid를 형식 정보에 매핑하는 지정 된 수의 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d81e4-104">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d81e4-105">구문</span><span class="sxs-lookup"><span data-stu-id="d81e4-105">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d81e4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d81e4-106">Parameters</span></span>  

 `celt`  
 <span data-ttu-id="d81e4-107">진행 검색할 GUID-형식 매핑 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d81e4-107">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="d81e4-108">제한이 각각 Windows 런타임 GUID를 해당 ICorDebugType 개체에 매핑하는 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="d81e4-108">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="d81e4-109">제한이 에 실제로 반환 된 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 개체 수에 대 한 포인터입니다 `values` .</span><span class="sxs-lookup"><span data-stu-id="d81e4-109">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d81e4-110">설명</span><span class="sxs-lookup"><span data-stu-id="d81e4-110">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d81e4-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d81e4-111">Requirements</span></span>  

 <span data-ttu-id="d81e4-112">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="d81e4-112">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="d81e4-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d81e4-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d81e4-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d81e4-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d81e4-115">**.NET Framework 버전:**[!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d81e4-115">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d81e4-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d81e4-116">See also</span></span>

- [<span data-ttu-id="d81e4-117">ICorDebugGuidToTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d81e4-117">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="d81e4-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d81e4-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
