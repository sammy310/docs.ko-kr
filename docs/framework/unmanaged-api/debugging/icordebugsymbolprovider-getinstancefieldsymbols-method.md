---
title: ICorDebugSymbolProvider::GetInstanceFieldSymbols 메서드
ms.date: 03/30/2017
ms.assetid: a29b9233-ee67-4b53-b8bc-c00b281e7edb
ms.openlocfilehash: 1a74b355b695f65166d0fe63bbdd41d789db5cfe
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730866"
---
# <a name="icordebugsymbolprovidergetinstancefieldsymbols-method"></a><span data-ttu-id="9e4a2-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="9e4a2-102">ICorDebugSymbolProvider::GetInstanceFieldSymbols Method</span></span>

<span data-ttu-id="9e4a2-103">typespec 서명에 해당하는 인스턴스 필드 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-103">Gets the instance field symbols that correspond to a typespec signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9e4a2-104">구문</span><span class="sxs-lookup"><span data-stu-id="9e4a2-104">Syntax</span></span>  
  
```cpp  
HRESULT GetInstanceFieldSymbols(  
   [in] ULONG32 cbSignature,  
   [in, size_is(cbSignature)]  BYTE typeSig[],  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugInstanceFieldSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9e4a2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9e4a2-105">Parameters</span></span>  

 `cbSignature`  
 <span data-ttu-id="9e4a2-106">[in] `typeSig` 배열의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-106">[in] The number of bytes in the `typeSig` array.</span></span>  
  
 `typeSig`  
 <span data-ttu-id="9e4a2-107">[in] `typespec` 서명이 들어 있는 바이트 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-107">[in] A byte array that contains the `typespec` signature.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="9e4a2-108">[in] 요청된 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-108">[in] The number of symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="9e4a2-109">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-109">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pSymbols`  
 <span data-ttu-id="9e4a2-110">제한이 요청 된 인스턴스 필드 기호를 포함 하는 [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-110">[out] A pointer to an [ICorDebugStaticFieldSymbol](icordebugstaticfieldsymbol-interface.md) array that contains the requested instance field symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9e4a2-111">설명</span><span class="sxs-lookup"><span data-stu-id="9e4a2-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="9e4a2-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9e4a2-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9e4a2-113">Requirements</span></span>  

 <span data-ttu-id="9e4a2-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9e4a2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9e4a2-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="9e4a2-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="9e4a2-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="9e4a2-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="9e4a2-117">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9e4a2-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9e4a2-118">참조</span><span class="sxs-lookup"><span data-stu-id="9e4a2-118">See also</span></span>

- [<span data-ttu-id="9e4a2-119">GetStaticFieldSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="9e4a2-119">GetStaticFieldSymbols Method</span></span>](icordebugsymbolprovider-getstaticfieldsymbols-method.md)
- [<span data-ttu-id="9e4a2-120">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e4a2-120">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="9e4a2-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9e4a2-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
