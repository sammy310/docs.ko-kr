---
title: ICorDebugVariableSymbol::GetName 메서드
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: abc0e368f259df1a3542b0fc8e7fbfd7e06cf6eb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178450"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="54e9a-102">ICorDebugVariableSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="54e9a-102">ICorDebugVariableSymbol::GetName Method</span></span>
<span data-ttu-id="54e9a-103">변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="54e9a-103">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="54e9a-104">구문</span><span class="sxs-lookup"><span data-stu-id="54e9a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="54e9a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="54e9a-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="54e9a-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="54e9a-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="54e9a-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="54e9a-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="54e9a-108">변수 이름이 포함된 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="54e9a-108">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="54e9a-109">설명</span><span class="sxs-lookup"><span data-stu-id="54e9a-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="54e9a-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="54e9a-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="54e9a-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="54e9a-111">Requirements</span></span>  
 <span data-ttu-id="54e9a-112">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="54e9a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54e9a-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="54e9a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="54e9a-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="54e9a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="54e9a-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="54e9a-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54e9a-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="54e9a-116">See also</span></span>

- [<span data-ttu-id="54e9a-117">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54e9a-117">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="54e9a-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="54e9a-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
