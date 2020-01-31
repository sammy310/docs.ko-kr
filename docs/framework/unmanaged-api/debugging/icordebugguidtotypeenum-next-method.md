---
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
ms.openlocfilehash: 76cab0b8b5f16f24c62e31be2707c95c7e557034
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76777635"
---
# <a name="icordebugguidtotypeenumnext-method"></a><span data-ttu-id="fac21-102">ICorDebugGuidToTypeEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="fac21-102">ICorDebugGuidToTypeEnum::Next Method</span></span>
<span data-ttu-id="fac21-103">Guid를 형식 정보에 매핑하는 지정 된 수의 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 인스턴스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fac21-103">Gets the specified number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) instances that map GUIDs to type information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fac21-104">구문</span><span class="sxs-lookup"><span data-stu-id="fac21-104">Syntax</span></span>  
  
```cpp  
HRESULT Next(  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched] CorDebugGuidToTypeMapping values[  ],  
    [out] ULONG *pceltFetched  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fac21-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fac21-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="fac21-106">진행 검색할 GUID-형식 매핑 개체의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fac21-106">[in] The number of GUID-to-type mapping objects to be retrieved.</span></span>  
  
 `values`  
 <span data-ttu-id="fac21-107">제한이 각각 Windows 런타임 GUID를 해당 ICorDebugType 개체에 매핑하는 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="fac21-107">[out] An array of pointers, each of which points to a [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) object that maps a Windows Runtime GUID to its corresponding ICorDebugType object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="fac21-108">제한이 `values`에서 실제로 반환 된 [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) 개체 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fac21-108">[out] A pointer to the number of [CorDebugGuidToTypeMapping](cordebugguidtotypemapping-structure.md) objects actually returned in `values`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fac21-109">주의</span><span class="sxs-lookup"><span data-stu-id="fac21-109">Remarks</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fac21-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fac21-110">Requirements</span></span>  
 <span data-ttu-id="fac21-111">**플랫폼:** Windows 런타임</span><span class="sxs-lookup"><span data-stu-id="fac21-111">**Platforms:** Windows Runtime</span></span>  
  
 <span data-ttu-id="fac21-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fac21-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fac21-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fac21-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fac21-114">**.NET Framework 버전:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac21-114">**.NET Framework Versions:** [!INCLUDE[net_current_v45plus](../../../../includes/net-current-v45plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac21-115">참조</span><span class="sxs-lookup"><span data-stu-id="fac21-115">See also</span></span>

- [<span data-ttu-id="fac21-116">ICorDebugGuidToTypeEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac21-116">ICorDebugGuidToTypeEnum Interface</span></span>](icordebugguidtotypeenum-interface.md)
- [<span data-ttu-id="fac21-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac21-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
