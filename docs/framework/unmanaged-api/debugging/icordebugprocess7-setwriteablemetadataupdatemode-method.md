---
description: '자세히 알아보기: ICorDebugProcess7:: SetWriteableMetadataUpdateMode 메서드'
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
ms.openlocfilehash: 86ece68e160fbd61f44adcf495656c7b5d6b5153
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99691265"
---
# <a name="icordebugprocess7setwriteablemetadataupdatemode-method"></a><span data-ttu-id="2dd21-103">ICorDebugProcess7::SetWriteableMetadataUpdateMode 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd21-103">ICorDebugProcess7::SetWriteableMetadataUpdateMode Method</span></span>

<span data-ttu-id="2dd21-104">[.NET Framework 4.5.2 이상 버전에서 지원됨]</span><span class="sxs-lookup"><span data-stu-id="2dd21-104">[Supported in the .NET Framework 4.5.2 and later versions]</span></span>  
  
 <span data-ttu-id="2dd21-105">대상 프로세스 내에서 디버거가 메타데이터에 대한 메모리 내 업데이트를 처리하는 방법을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd21-105">Configures how the debugger handles in-memory updates to metadata within the target process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2dd21-106">구문</span><span class="sxs-lookup"><span data-stu-id="2dd21-106">Syntax</span></span>  
  
```cpp
HRESULT SetWriteableMetadataUpdateMode(  
   WriteableMetadataUpdateMode flags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2dd21-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2dd21-107">Parameters</span></span>  

 `flags`  
 <span data-ttu-id="2dd21-108">대상 [](writeablemetadataupdatemode-enumeration.md) 프로세스에서 메타 데이터에 대 한 메모리 내 업데이트가 디버거에 표시 되는지 ( `WriteableMetadataUpdateMode::AlwaysShowUpdates` ) 아니면 표시 되지 않는지 ()를 지정 하는 WriteableMetadataUpdateMode 열거형 값입니다 `WriteableMetadataUpdateMode::LegacyCompatPolicy` .</span><span class="sxs-lookup"><span data-stu-id="2dd21-108">A [WriteableMetadataUpdateMode](writeablemetadataupdatemode-enumeration.md) enumeration value that specifies whether in-memory updates to metadata in the target process are visible (`WriteableMetadataUpdateMode::AlwaysShowUpdates`) or not visible (`WriteableMetadataUpdateMode::LegacyCompatPolicy`) to the debugger.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2dd21-109">설명</span><span class="sxs-lookup"><span data-stu-id="2dd21-109">Remarks</span></span>  

 <span data-ttu-id="2dd21-110">대상 프로세스의 메타데이터는 편집하며 계속하기, 프로파일러 또는 <xref:System.Reflection.Emit?displayProperty=nameWithType>에 의해 업데이트될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2dd21-110">Updates to the metadata of the target process can come from Edit and Continue, a profiler, or <xref:System.Reflection.Emit?displayProperty=nameWithType>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2dd21-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dd21-111">Requirements</span></span>  

 <span data-ttu-id="2dd21-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dd21-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dd21-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2dd21-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2dd21-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2dd21-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2dd21-115">**.NET Framework 버전:**[!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dd21-115">**.NET Framework Versions:** [!INCLUDE[net_current_v452plus](../../../../includes/net-current-v452plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd21-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2dd21-116">See also</span></span>

- [<span data-ttu-id="2dd21-117">ICorDebugProcess7 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dd21-117">ICorDebugProcess7 Interface</span></span>](icordebugprocess7-interface.md)
- [<span data-ttu-id="2dd21-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dd21-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
