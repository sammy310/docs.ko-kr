---
title: ICorDebugSymbolProvider::GetStaticFieldSymbols 메서드
ms.date: 03/30/2017
ms.assetid: b178367f-a6e4-413c-b06f-daf3804b456b
ms.openlocfilehash: 02cc62a421058f83e28ce945ae9e76745f768988
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791560"
---
# <a name="icordebugsymbolprovidergetstaticfieldsymbols-method"></a><span data-ttu-id="fded1-102">ICorDebugSymbolProvider::GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="fded1-102">ICorDebugSymbolProvider::GetStaticFieldSymbols Method</span></span>
<span data-ttu-id="fded1-103">typespec 서명에 해당하는 정적 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fded1-103">Gets the static field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fded1-104">구문</span><span class="sxs-lookup"><span data-stu-id="fded1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetStaticFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugStaticFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fded1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fded1-105">Parameters</span></span>  
 `cbSignature`  
 <span data-ttu-id="fded1-106">[in] `typeSig` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fded1-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="fded1-107">[in] `typespec` 서명이 들어 있는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="fded1-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="fded1-108">[in] 요청된 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="fded1-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="fded1-109">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fded1-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="fded1-110">제한이 요청 된 정적 필드 기호를 포함 하는 [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="fded1-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested static field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="fded1-111">주의</span><span class="sxs-lookup"><span data-stu-id="fded1-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="fded1-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fded1-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fded1-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fded1-113">Requirements</span></span>  
 <span data-ttu-id="fded1-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fded1-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fded1-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="fded1-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="fded1-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="fded1-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="fded1-117">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fded1-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fded1-118">참조</span><span class="sxs-lookup"><span data-stu-id="fded1-118">See also</span></span>

- [<span data-ttu-id="fded1-119">GetInstanceFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="fded1-119">GetInstanceFieldSymbols Method</span></span>](icordebugsymbolprovider-getinstancefieldsymbols-method.md)
- [<span data-ttu-id="fded1-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fded1-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="fded1-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fded1-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
