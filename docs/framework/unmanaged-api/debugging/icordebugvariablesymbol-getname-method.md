---
description: '자세히 알아보기: ICorDebugVariableSymbol:: GetName 메서드'
title: ICorDebugVariableSymbol::GetName 메서드
ms.date: 03/30/2017
ms.assetid: c922b7d4-44e5-45e4-aef3-cc9c35a0be80
ms.openlocfilehash: 4a3ba1dfebd256dcbb8374634a52f1feca5d9611
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790596"
---
# <a name="icordebugvariablesymbolgetname-method"></a><span data-ttu-id="20541-103">ICorDebugVariableSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="20541-103">ICorDebugVariableSymbol::GetName Method</span></span>

<span data-ttu-id="20541-104">변수의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="20541-104">Gets the name of a variable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="20541-105">구문</span><span class="sxs-lookup"><span data-stu-id="20541-105">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="20541-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="20541-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="20541-107">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="20541-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="20541-108">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20541-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="20541-109">변수 이름이 포함된 문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="20541-109">A pointer to a character array that contains the variable name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="20541-110">설명</span><span class="sxs-lookup"><span data-stu-id="20541-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="20541-111">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="20541-111">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="20541-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="20541-112">Requirements</span></span>  

 <span data-ttu-id="20541-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="20541-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="20541-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="20541-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="20541-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="20541-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="20541-116">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="20541-116">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="20541-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="20541-117">See also</span></span>

- [<span data-ttu-id="20541-118">ICorDebugVariableSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20541-118">ICorDebugVariableSymbol Interface</span></span>](icordebugvariablesymbol-interface.md)
- [<span data-ttu-id="20541-119">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="20541-119">Debugging Interfaces</span></span>](debugging-interfaces.md)
