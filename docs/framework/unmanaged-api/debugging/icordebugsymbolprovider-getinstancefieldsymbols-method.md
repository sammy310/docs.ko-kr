---
title: 'Icordebugsymbolprovider:: Getinstancefieldsymbols 메서드'
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02ffabfc43861d3d295a0bd2ea09213b06b6868a
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67771417"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="5c13e-102">Icordebugsymbolprovider:: Getinstancefieldsymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="5c13e-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>
<span data-ttu-id="5c13e-103">typespec 서명에 해당하는 인스턴스 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5c13e-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5c13e-104">구문</span><span class="sxs-lookup"><span data-stu-id="5c13e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5c13e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5c13e-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="5c13e-106">[in] `typeSig` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5c13e-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="5c13e-107">[in] `typespec` 서명이 들어 있는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5c13e-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="5c13e-108">[in] 요청된 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="5c13e-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="5c13e-109">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5c13e-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="5c13e-110">[out] 에 대 한 포인터를 [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) 요청한 인스턴스 필드 기호를 포함 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="5c13e-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5c13e-111">설명</span><span class="sxs-lookup"><span data-stu-id="5c13e-111">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5c13e-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5c13e-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5c13e-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5c13e-113">Requirements</span></span>  
 <span data-ttu-id="5c13e-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5c13e-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5c13e-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5c13e-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5c13e-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5c13e-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5c13e-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5c13e-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5c13e-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="5c13e-118">See also</span></span>

- [<span data-ttu-id="5c13e-119">GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="5c13e-119">GetStaticFieldSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="5c13e-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c13e-120">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="5c13e-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5c13e-121">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
