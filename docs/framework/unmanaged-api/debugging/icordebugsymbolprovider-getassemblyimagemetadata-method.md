---
title: 'ICorDebugSymbolProvider:: GetAssemblyImageMetadata 메서드'
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: fb08df3b594e0c34dfe4ca791983b0c111239b23
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138907"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="6f0bc-102">ICorDebugSymbolProvider:: GetAssemblyImageMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="6f0bc-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="6f0bc-103">병합된 어셈블리에서 메타데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6f0bc-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6f0bc-104">구문</span><span class="sxs-lookup"><span data-stu-id="6f0bc-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6f0bc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6f0bc-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="6f0bc-106">제한이 병합 된 어셈블리의 메타 데이터 크기와 주소에 대 한 정보를 포함 하는 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6f0bc-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6f0bc-107">주의</span><span class="sxs-lookup"><span data-stu-id="6f0bc-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6f0bc-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f0bc-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6f0bc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f0bc-109">Requirements</span></span>  
 <span data-ttu-id="6f0bc-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f0bc-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6f0bc-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6f0bc-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6f0bc-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6f0bc-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6f0bc-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6f0bc-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f0bc-114">참조</span><span class="sxs-lookup"><span data-stu-id="6f0bc-114">See also</span></span>

- [<span data-ttu-id="6f0bc-115">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f0bc-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6f0bc-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6f0bc-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
