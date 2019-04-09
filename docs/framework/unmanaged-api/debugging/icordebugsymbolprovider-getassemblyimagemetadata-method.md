---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0be0722db374ff49541b3c4b68f295774f34163e
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59104132"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="6475d-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="6475d-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="6475d-103">병합된 어셈블리에서 메타데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6475d-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6475d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6475d-104">Syntax</span></span>  
  
```  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6475d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6475d-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="6475d-106">[out] 주소에 대 한 포인터를 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) 크기와 병합된 된 어셈블리의 메타 데이터의 주소에 대 한 정보를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6475d-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6475d-107">설명</span><span class="sxs-lookup"><span data-stu-id="6475d-107">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="6475d-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6475d-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6475d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6475d-109">Requirements</span></span>  
 <span data-ttu-id="6475d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="6475d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6475d-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6475d-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6475d-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6475d-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="6475d-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="6475d-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="6475d-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="6475d-114">See also</span></span>

- [<span data-ttu-id="6475d-115">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6475d-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6475d-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6475d-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
