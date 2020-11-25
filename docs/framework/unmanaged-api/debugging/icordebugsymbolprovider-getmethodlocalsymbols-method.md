---
title: ICorDebugSymbolProvider::GetMethodLocalSymbols 메서드
ms.date: 03/30/2017
ms.assetid: 8b989e38-e779-49d1-9e90-f1f920484b08
ms.openlocfilehash: c5a21436c939ddfca0219618efe64d9e0e40aef4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730853"
---
# <a name="icordebugsymbolprovidergetmethodlocalsymbols-method"></a><span data-ttu-id="6710f-102">ICorDebugSymbolProvider::GetMethodLocalSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="6710f-102">ICorDebugSymbolProvider::GetMethodLocalSymbols Method</span></span>

<span data-ttu-id="6710f-103">메서드의 RVA(상대 가상 주소)가 지정된 경우 해당 메서드의 로컬 기호를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6710f-103">Gets a method's local symbols given the relative virtual address (RVA) of that method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6710f-104">구문</span><span class="sxs-lookup"><span data-stu-id="6710f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodLocalSymbols(  
   [in] ULONG32 nativeRVA,  
   [in] ULONG32 cRequestedSymbols,  
   [out] ULONG32 *pcFetchedSymbols,  
   [out, size_is(cRequestedSymbols), length_is(*pcFetchedSymbols)] ICorDebugVariableSymbol *pSymbols[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6710f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6710f-105">Parameters</span></span>  

 `nativeRVA`  
 <span data-ttu-id="6710f-106">[in] 메서드의 기본 상대 가상 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="6710f-106">[in] The native relative virtual address of the method.</span></span>  
  
 `cRequestedSymbols`  
 <span data-ttu-id="6710f-107">[in] 요청되는 로컬 기호 수입니다.</span><span class="sxs-lookup"><span data-stu-id="6710f-107">[in] The number of local symbols requested.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="6710f-108">[out] 메서드에 의해 검색되는 기호 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6710f-108">[out] A pointer to the number of symbols retrieved by the method.</span></span>  
  
 `pcFetchedSymbols`  
 <span data-ttu-id="6710f-109">제한이 메서드의 로컬 기호를 포함 하는 [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) 배열에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6710f-109">[out] A pointer to an [ICorDebugVariableSymbol](icordebugvariablesymbol-interface.md) array that contains the method's local symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6710f-110">설명</span><span class="sxs-lookup"><span data-stu-id="6710f-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6710f-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6710f-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6710f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6710f-112">Requirements</span></span>  

 <span data-ttu-id="6710f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6710f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6710f-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="6710f-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="6710f-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="6710f-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="6710f-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6710f-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6710f-117">참조</span><span class="sxs-lookup"><span data-stu-id="6710f-117">See also</span></span>

- [<span data-ttu-id="6710f-118">GetMethodParameterSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="6710f-118">GetMethodParameterSymbols Method</span></span>](icordebugsymbolprovider-getmethodparametersymbols-method.md)
- [<span data-ttu-id="6710f-119">ICorDebugSymbolProvider 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6710f-119">ICorDebugSymbolProvider Interface</span></span>](icordebugsymbolprovider-interface.md)
- [<span data-ttu-id="6710f-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6710f-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
