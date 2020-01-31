---
title: ICorDebugDataTarget2::GetSymbolProviderForImage 메서드
ms.date: 03/30/2017
ms.assetid: b7c0a2f0-e904-43b3-98e1-d669e8a589e8
ms.openlocfilehash: bada60295c3a9b3a702aa674e06f8f5cf6ac0a24
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76788821"
---
# <a name="icordebugdatatarget2getsymbolproviderforimage-method"></a><span data-ttu-id="69068-102">ICorDebugDataTarget2::GetSymbolProviderForImage 메서드</span><span class="sxs-lookup"><span data-stu-id="69068-102">ICorDebugDataTarget2::GetSymbolProviderForImage Method</span></span>
<span data-ttu-id="69068-103">모듈의 시스템 공급자를 해당 모듈의 기본 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="69068-103">Returns the symbol-provider for a module from the base address of that module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69068-104">구문</span><span class="sxs-lookup"><span data-stu-id="69068-104">Syntax</span></span>  
  
```cpp  
HRESULT GetSymbolProviderForImage(  
    [in] CORDB_ADDRESS imageBaseAddress,   
    [out] ICorDebugSymbolProvider **ppSymProvider  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69068-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69068-105">Parameters</span></span>  
 `imageBaseAddress`  
 <span data-ttu-id="69068-106">진행 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="69068-106">[in] A [CORDB_ADDRESS](../../../../docs/framework/unmanaged-api/common-data-types-unmanaged-api-reference.md) value that represents the base address of a module.</span></span>  
  
 `ppSymProvider`  
 <span data-ttu-id="69068-107">제한이 [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="69068-107">[out] A pointer to the address of an [ICorDebugSymbolProvider](icordebugsymbolprovider-interface.md) object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="69068-108">주의</span><span class="sxs-lookup"><span data-stu-id="69068-108">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="69068-109">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69068-109">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69068-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69068-110">Requirements</span></span>  
 <span data-ttu-id="69068-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69068-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69068-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="69068-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="69068-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="69068-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="69068-114">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69068-114">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69068-115">참조</span><span class="sxs-lookup"><span data-stu-id="69068-115">See also</span></span>

- [<span data-ttu-id="69068-116">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69068-116">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="69068-117">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69068-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
