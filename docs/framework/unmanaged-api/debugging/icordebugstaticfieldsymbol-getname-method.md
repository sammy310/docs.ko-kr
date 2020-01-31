---
title: ICorDebugStaticFieldSymbol::GetName 메서드
ms.date: 03/30/2017
ms.assetid: e2be4af2-15d1-4e6a-8b68-1d78c93294a4
ms.openlocfilehash: 0e4c52ff1ae6113ee2c3990a9d91682e10141902
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76791824"
---
# <a name="icordebugstaticfieldsymbolgetname-method"></a><span data-ttu-id="e3cb6-102">ICorDebugStaticFieldSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="e3cb6-102">ICorDebugStaticFieldSymbol::GetName Method</span></span>
<span data-ttu-id="e3cb6-103">정적 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb6-103">Gets the name of the static field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e3cb6-104">구문</span><span class="sxs-lookup"><span data-stu-id="e3cb6-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e3cb6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e3cb6-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="e3cb6-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb6-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="e3cb6-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb6-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="e3cb6-108">[out] 반환된 이름을 저장하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb6-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e3cb6-109">주의</span><span class="sxs-lookup"><span data-stu-id="e3cb6-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="e3cb6-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e3cb6-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e3cb6-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e3cb6-111">Requirements</span></span>  
 <span data-ttu-id="e3cb6-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e3cb6-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3cb6-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e3cb6-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e3cb6-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e3cb6-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="e3cb6-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3cb6-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3cb6-116">참조</span><span class="sxs-lookup"><span data-stu-id="e3cb6-116">See also</span></span>

- [<span data-ttu-id="e3cb6-117">ICorDebugStaticFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3cb6-117">ICorDebugStaticFieldSymbol Interface</span></span>](icordebugstaticfieldsymbol-interface.md)
- [<span data-ttu-id="e3cb6-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e3cb6-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
