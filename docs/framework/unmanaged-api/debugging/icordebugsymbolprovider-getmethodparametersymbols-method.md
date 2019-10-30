---
title: 'ICorDebugSymbolProvider:: GetMethodParameterSymbols 메서드'
ms.date: 03/30/2017
ms.assetid: 58b7c0b9-f6ad-4b49-b92d-0e421cfd0ec6
ms.openlocfilehash: 1f7da156e5a164dc753e2283bc7ab24d18983173
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138837"
---
# <a name="icordebugsymbolprovidergetmethodparametersymbols-method"></a><span data-ttu-id="47c40-102">ICorDebugSymbolProvider:: GetMethodParameterSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="47c40-102">ICorDebugSymbolProvider::GetMethodParameterSymbols Method</span></span>
<span data-ttu-id="47c40-103">메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 매개 변수 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="47c40-103">Gets a method's parameter symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47c40-104">구문</span><span class="sxs-lookup"><span data-stu-id="47c40-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodParameterSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47c40-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47c40-105">Parameters</span></span>  
 `nativeRVA`  
 <span data-ttu-id="47c40-106">[in] 메서드의 기본 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="47c40-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="47c40-107">[in] 요청되는 로컬 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="47c40-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="47c40-108">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="47c40-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="47c40-109">제한이 메서드의 로컬 기호를 포함 하는 [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="47c40-109">[out] A pointer to an [ICorDebugVariableSymbol](../../../../docs/framework/unmanaged-api/debugging/icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47c40-110">주의</span><span class="sxs-lookup"><span data-stu-id="47c40-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="47c40-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47c40-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47c40-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47c40-112">Requirements</span></span>  
 <span data-ttu-id="47c40-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47c40-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47c40-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="47c40-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="47c40-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="47c40-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="47c40-116">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47c40-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47c40-117">참조</span><span class="sxs-lookup"><span data-stu-id="47c40-117">See also</span></span>

- [<span data-ttu-id="47c40-118">GetMethodLocalSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="47c40-118">GetMethodLocalSymbols Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-getmethodlocalsymbols-method.md)
- [<span data-ttu-id="47c40-119">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47c40-119">ICorDebugSymbolProvider Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="47c40-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47c40-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
