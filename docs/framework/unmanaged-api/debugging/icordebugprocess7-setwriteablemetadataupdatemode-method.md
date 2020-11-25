---
title: ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ICorDebugProcess7.SetWriteableMetadataUpdateMode
api_location:
- mscordbi.dll
api_type:
- COM
ms.assetid: 8589bba7-7304-45ba-9e31-7bf43dfd5c19
topic_type:
- apiref
ms.openlocfilehash: 5671f8cb51210c27dffdedba28b4b145b3fedc55
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732556"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="85517-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드</span><span class="sxs-lookup"><span data-stu-id="85517-102">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>

<span data-ttu-id="85517-103">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="85517-103">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="85517-104">대상 프로세스 내에서 디버거가 메타데이터에 대한 메모리 내 업데이트를 처리하는 방법을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="85517-104">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="85517-105">구문</span><span class="sxs-lookup"><span data-stu-id="85517-105">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="85517-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="85517-106">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="85517-107">대상 [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) 프로세스에서 메타 데이터에 대 한 메모리 내 업데이트가 디버거에 표시 되는지 ( `WriteableMetadataUpdateMode::AlwaysShowUpdates` ) 아니면 표시 되지 않는지 ()를 지정 하는 WriteableMetadataUpdateMode 열거형 값입니다 `WriteableMetadataUpdateMode::LegacyCompatPolicy` .</span><span class="sxs-lookup"><span data-stu-id="85517-107">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="85517-108">설명</span><span class="sxs-lookup"><span data-stu-id="85517-108">Remarks</span></span>  

 <span data-ttu-id="85517-109">대상 프로세스의 메타데이터는 편집하며 계속하기, 프로파일러 또는 <xref:System.Reflection.Emit?displayProperty=nameWithType>에 의해 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85517-109">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="85517-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="85517-110">Requirements</span></span>  

 <span data-ttu-id="85517-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="85517-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="85517-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="85517-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="85517-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="85517-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="85517-114">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="85517-114">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="85517-115">참조</span><span class="sxs-lookup"><span data-stu-id="85517-115">See also</span></span>

- [<span data-ttu-id="85517-116">ICorDebugProcess7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85517-116">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="85517-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="85517-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
