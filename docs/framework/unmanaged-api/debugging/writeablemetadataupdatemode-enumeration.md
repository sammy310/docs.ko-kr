---
title: WriteableMetadataUpdateMode 열거형
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- WriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 6758f4d3-6bc7-4c99-8582-e9be00566784
topic_type:
- apiref
ms.openlocfilehash: 98566176ff33000fc4b4587b5669a037c90268f5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73139101"
---
# <a name="writeablemetadataupdatemode-enumeration"></a><span data-ttu-id="63af7-102">WriteableMetadataUpdateMode 열거형</span><span class="sxs-lookup"><span data-stu-id="63af7-102">WriteableMetadataUpdateMode Enumeration</span></span>
<span data-ttu-id="63af7-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="63af7-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="63af7-104">메타데이터에 대한 메모리 내 업데이트가 디버거에 표시되는지 여부를 지정하는 값을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-104">Provides values that specify whether in-memory updates to metadata are visible to a debugger.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63af7-105">구문</span><span class="sxs-lookup"><span data-stu-id="63af7-105">Syntax</span></span>  
  
```cpp
typedef enum WriteableMetadataUpdateMode {  
   LegacyCompatPolicy,  
   AlwaysShowUpdates  
} WriteableMetadataUpdateMode;  
```  
  
## <a name="members"></a><span data-ttu-id="63af7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="63af7-106">Members</span></span>  
  
|<span data-ttu-id="63af7-107">멤버 이름</span><span class="sxs-lookup"><span data-stu-id="63af7-107">Member name</span></span>|<span data-ttu-id="63af7-108">설명</span><span class="sxs-lookup"><span data-stu-id="63af7-108">Description</span></span>|  
|-----------------|-----------------|  
|`LegacyCompatPolicy`|<span data-ttu-id="63af7-109">메타데이터에 대한 메모리 내 업데이트를 표시할 때 .NET Framework 이전 버전과의 호환성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-109">Maintain compatibility with previous versions of the .NET Framework when making in-memory updates to metadata visible.</span></span> <span data-ttu-id="63af7-110">자세한 내용은 설명 부분을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63af7-110">See the Remarks section for more information.</span></span>|  
|`AlwaysShowUpdates`|<span data-ttu-id="63af7-111">메타데이터에 대한 메모리 내 업데이트를 디버거에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-111">Make in-memory updates to metadata visible to the debugger.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="63af7-112">주의</span><span class="sxs-lookup"><span data-stu-id="63af7-112">Remarks</span></span>  
 <span data-ttu-id="63af7-113">`WriteableMetadataUpdateMode` 열거형의 멤버를 [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) 메서드에 전달 하 여 대상 프로세스에서 메타 데이터에 대 한 메모리 내 업데이트가 디버거에 표시 되는지 여부를 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-113">A member of the `WriteableMetadataUpdateMode` enumeration can be passed to the [SetWriteableMetadataUpdateMode](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md) method to control whether in-memory updates to metadata in the target process are visible to the debugger.</span></span>  
  
 <span data-ttu-id="63af7-114">`LegacyCompatPolicy` 옵션은 .NET Framework 4.5.2 이전 버전에서와 같은 동작을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-114">The `LegacyCompatPolicy` option enforces the same behavior as in versions of the .NET Framework before 4.5.2.</span></span> <span data-ttu-id="63af7-115">이로 인해 업데이트의 메타데이터가 표시되지 않는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-115">This often means that metadata from updates is not visible.</span></span> <span data-ttu-id="63af7-116">그러나 여러 디버깅 메서드를 호출하면 디버거가 업데이트를 표시하도록 암시적으로 강제 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-116">However, calls to a number of debugging methods implicitly coerce the debugger to make updates visible.</span></span> <span data-ttu-id="63af7-117">예를 들어, 디버거가 [ICorDebugILFrame:: GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) 을 전달 하는 경우 메서드의 원래 메타 데이터에 없는 변수의 인덱스는 모듈에 대 한 모든 메타 데이터가 프로세스의 현재 상태와 일치 하는 스냅숏으로 업데이트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-117">For example, if the debugger passes [ICorDebugILFrame::GetLocalVariable](../../../../docs/framework/unmanaged-api/debugging/icordebugilframe-getlocalvariable-method.md) the index of a variable not found in the method's original metadata, all metadata for the module is updated to a snapshot matching the current state of the process.</span></span> <span data-ttu-id="63af7-118">다시 말해서, `LegacyCompatPolicy` 옵션을 사용하는 경우에는 디버거가 관리되지 않는 디버깅 API의 다른 부분을 사용하는 방식에 따라 사용 가능한 메타데이터 업데이트가 표시되지 않을 수도 있고 일부 또는 모든 업데이트가 표시될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63af7-118">In other words, with the `LegacyCompatPolicy` option, the debugger might see none, some, or all of the available metadata updates, depending on how it uses other parts of the unmanaged debugging API.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="63af7-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63af7-119">Requirements</span></span>  
 <span data-ttu-id="63af7-120">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63af7-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63af7-121">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="63af7-121">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="63af7-122">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="63af7-122">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="63af7-123">**.NET Framework 버전:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="63af7-123">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63af7-124">참조</span><span class="sxs-lookup"><span data-stu-id="63af7-124">See also</span></span>

- [<span data-ttu-id="63af7-125">디버깅 열거형</span><span class="sxs-lookup"><span data-stu-id="63af7-125">Debugging Enumerations</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-enumerations.md)
- [<span data-ttu-id="63af7-126">SetWriteableMetadataUpdateMode 메서드</span><span class="sxs-lookup"><span data-stu-id="63af7-126">SetWriteableMetadataUpdateMode Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugprocess7-setwriteablemetadataupdatemode-method.md)
