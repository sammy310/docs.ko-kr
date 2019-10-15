---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fea08331fffb85c91721d60764bae8bfe8b30e27
ms.sourcegitcommit: 33c8d6f7342a4bb2c577842b7f075b0e20a2fa40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2019
ms.locfileid: "70928811"
---
# <a name="ilcodekind-enumeration"></a><span data-ttu-id="43f74-102">ILCodeKind 열거형</span><span class="sxs-lookup"><span data-stu-id="43f74-102">ILCodeKind Enumeration</span></span>
<span data-ttu-id="43f74-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="43f74-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="43f74-104">디버거가 프로파일러 ReJIT 계측에 추가된 로컬 변수나 코드에 액세스할 수 있는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="43f74-104">Provides values that specify whether the debugger is able to access local variables or code added in profiler ReJIT instrumentation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43f74-105">구문</span><span class="sxs-lookup"><span data-stu-id="43f74-105">Syntax</span></span>  
  
```cpp
typedef enum ILCodeKind {  
   ILCODE_ORIGINAL_IL = 0x1,  
   ILCODE_REJIT_IL = 0x2,  
} ILCodeKind;  
```  
  
## <a name="members"></a><span data-ttu-id="43f74-106">멤버</span><span class="sxs-lookup"><span data-stu-id="43f74-106">Members</span></span>  
  
|<span data-ttu-id="43f74-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="43f74-107">Member name</span></span>|<span data-ttu-id="43f74-108">Description</span><span class="sxs-lookup"><span data-stu-id="43f74-108">Description</span></span>|  
|-----------------|-----------------|  
|`ILCODE_ORIGINAL_IL`|<span data-ttu-id="43f74-109">디버거가 ReJIT 계측의 정보에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="43f74-109">The debugger does not have access to information from ReJIT instrumentation.</span></span>|  
|`ILCODE_REJIT_IL`|<span data-ttu-id="43f74-110">디버거가 ReJIT 계측의 정보에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43f74-110">The debugger has access to information from ReJIT instrumentation.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43f74-111">설명</span><span class="sxs-lookup"><span data-stu-id="43f74-111">Remarks</span></span>  
 <span data-ttu-id="43f74-112">[EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) 및 [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) 메서드에 `ILCodeKind` 열거형의 멤버를 전달하여 디버거가 프로파일러 ReJIT 계측에 추가된 변수에 액세스할 수 있는지 여부를 확인하고 디버거가 계측된 IL에 액세스할 수 있는지 여부를 확인하는 [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) 메서드</span><span class="sxs-lookup"><span data-stu-id="43f74-112">A member of the `ILCodeKind` enumeration can be passed to the [EnumerateLocalVariablesEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-enumeratelocalvariablesex-method.md) and [GetLocalVariableEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getlocalvariableex-method.md) methods to determine whether the debugger can access variables added in profiler ReJIT instrumentation, and to the [GetCodeEx](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-getcodeex-method.md) method to determine whether the debugger can access instrumented IL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43f74-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="43f74-113">Requirements</span></span>  
 <span data-ttu-id="43f74-114">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="43f74-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43f74-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="43f74-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="43f74-116">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="43f74-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="43f74-117">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43f74-117">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43f74-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="43f74-118">See also</span></span>

- [<span data-ttu-id="43f74-119">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="43f74-119">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="43f74-120">ICorDebugILFrame4 인터페이스</span><span class="sxs-lookup"><span data-stu-id="43f74-120">ICorDebugILFrame4 Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe4-interface.md)
- [<span data-ttu-id="43f74-121">ReJIT 방법 가이드</span><span class="sxs-lookup"><span data-stu-id="43f74-121">ReJIT: A How-To Guide</span></span>](https://blogs.msdn.microsoft.com/davbr/2011/10/12/rejit-a-how-to-guide/)
