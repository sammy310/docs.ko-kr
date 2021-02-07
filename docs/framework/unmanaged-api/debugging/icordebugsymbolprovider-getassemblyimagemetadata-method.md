---
description: '자세히 알아보기: ICorDebugSymbolProvider:: GetAssemblyImageMetadata 메서드'
title: ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드
ms.date: 03/30/2017
ms.assetid: c3c9de67-b865-4ecf-b887-1f1d0719a0c0
ms.openlocfilehash: 4abe5cc2b2a31f89e6ca4f8fc643f26eac276515
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99717188"
---
# <a name="icordebugsymbolprovidergetassemblyimagemetadata-method"></a><span data-ttu-id="e4f87-103">ICorDebugSymbolProvider::GetAssemblyImageMetadata 메서드</span><span class="sxs-lookup"><span data-stu-id="e4f87-103">ICorDebugSymbolProvider::GetAssemblyImageMetadata Method</span></span>

<span data-ttu-id="e4f87-104">병합된 어셈블리에서 메타데이터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e4f87-104">Returns the metadata from a merged assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e4f87-105">구문</span><span class="sxs-lookup"><span data-stu-id="e4f87-105">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyImageMetadata(  
   [out] ICorDebugMemoryBuffer** ppMemoryBuffer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e4f87-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e4f87-106">Parameters</span></span>  

 `ppMemoryBuffer`  
 <span data-ttu-id="e4f87-107">제한이 병합 된 어셈블리의 메타 데이터 크기와 주소에 대 한 정보를 포함 하는 [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e4f87-107">[out] A pointer to the address of an [ICorDebugMemoryBuffer](icordebugmemorybuffer-interface.md) object that contains information about the size and address of the merged assembly's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e4f87-108">설명</span><span class="sxs-lookup"><span data-stu-id="e4f87-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e4f87-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e4f87-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e4f87-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e4f87-110">Requirements</span></span>  

 <span data-ttu-id="e4f87-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e4f87-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e4f87-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e4f87-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e4f87-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e4f87-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e4f87-114">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e4f87-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4f87-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e4f87-115">See also</span></span>

- [<span data-ttu-id="e4f87-116">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4f87-116">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="e4f87-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e4f87-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
