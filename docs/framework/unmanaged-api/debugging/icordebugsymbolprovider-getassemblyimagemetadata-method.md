---
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ad86c42d0f23de25fe0e5b9123a0dba3695d8d64
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964652"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="f4415-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="f4415-102">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>
<span data-ttu-id="f4415-103">병합된 어셈블리에서 메타데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-103">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f4415-104">구문</span><span class="sxs-lookup"><span data-stu-id="f4415-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f4415-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f4415-105">Parameters</span></span>  
 `ppMemoryBuffer`  
 <span data-ttu-id="f4415-106">제한이 병합 된 어셈블리의 메타 데이터 크기와 주소에 대 한 정보를 포함 하는 [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-106">[out] A pointer to the address of an [ICorDebugMemoryBuffer](../../../../docs/framework/unmanaged-api/debugging/icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f4415-107">설명</span><span class="sxs-lookup"><span data-stu-id="f4415-107">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="f4415-108">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f4415-108">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f4415-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f4415-109">Requirements</span></span>  
 <span data-ttu-id="f4415-110">**플랫폼** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f4415-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f4415-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f4415-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f4415-112">**라이브러리** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f4415-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f4415-113">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f4415-113">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f4415-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="f4415-114">See also</span></span>

- [<span data-ttu-id="f4415-115">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4415-115">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="f4415-116">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f4415-116">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
