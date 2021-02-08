---
description: '자세히 알아보기: ILCodeKind 열거형'
title: ILCodeKind 열거형
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ILCodeKind
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: b91765e4-82db-46f9-a6dc-6b80610276af
topic_type:
- apiref
ms.openlocfilehash: 2d3163b2c601c6f53d9a532fa877c014a67b3e18
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790466"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="af407-103">ILCodeKind 열거형</span><span class="sxs-lookup"><span data-stu-id="af407-103">ILCodeKind Enumeration</span></span>

<span data-ttu-id="af407-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="af407-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="af407-105">디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수나 코드에 액세스할 수 있는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="af407-105">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="af407-106">구문</span><span class="sxs-lookup"><span data-stu-id="af407-106">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="af407-107">구성원</span><span class="sxs-lookup"><span data-stu-id="af407-107">Members</span></span>  
  
|<span data-ttu-id="af407-108">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="af407-108">Member name</span></span>|<span data-ttu-id="af407-109">설명</span><span class="sxs-lookup"><span data-stu-id="af407-109">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="af407-110">디버거가 ReJIT 계측의 정보에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="af407-110">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="af407-111">디버거가 ReJIT 계측의 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af407-111">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="af407-112">설명</span><span class="sxs-lookup"><span data-stu-id="af407-112">Remarks</span></span>  

 <span data-ttu-id="af407-113">`ILCodeKind` [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) 및 [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) 메서드에 열거형의 멤버를 전달 하 여 디버거가 프로파일러 ReJIT 계측에 추가 된 변수에 액세스할 수 있는지 여부와 [getcodeex](icordebugilframe4-getcodeex-method.md) 메서드에 전달 하 여 디버거가 계측 된 IL에 액세스할 수 있는지 여부를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="af407-113">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="af407-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="af407-114">Requirements</span></span>  

 <span data-ttu-id="af407-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="af407-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="af407-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="af407-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="af407-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="af407-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="af407-118">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="af407-118">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="af407-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="af407-119">See also</span></span>

- [<span data-ttu-id="af407-120">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="af407-120">Debugging Enumerations</span></span>](debugging-enumerations.md)
- [<span data-ttu-id="af407-121">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="af407-121">ICorDebugILFrame4 Interface</span></span>](icordebugilframe4-interface.md)
- [<span data-ttu-id="af407-122">ReJIT: How-To 가이드</span><span class="sxs-lookup"><span data-stu-id="af407-122">ReJIT: A How-To Guide</span></span>](/archive/blogs/davbr/rejit-a-how-to-guide)
