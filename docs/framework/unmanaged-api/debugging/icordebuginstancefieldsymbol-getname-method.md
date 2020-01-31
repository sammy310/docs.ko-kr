---
title: ICorDebugInstanceFieldSymbol::GetName 메서드
ms.date: 03/30/2017
ms.assetid: d9c12b1f-9c1d-4943-8e9e-93b55faf085f
ms.openlocfilehash: 05914863dfbc2aca608a5d74f298f81c64345fe8
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76782382"
---
# <a name="icordebuginstancefieldsymbolgetname-method"></a><span data-ttu-id="b4a28-102">ICorDebugInstanceFieldSymbol::GetName 메서드</span><span class="sxs-lookup"><span data-stu-id="b4a28-102">ICorDebugInstanceFieldSymbol::GetName Method</span></span>
<span data-ttu-id="b4a28-103">인스턴스 필드의 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4a28-103">Gets the name of the instance field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4a28-104">구문</span><span class="sxs-lookup"><span data-stu-id="b4a28-104">Syntax</span></span>  
  
```cpp  
HRESULT GetName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4a28-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4a28-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="b4a28-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a28-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="b4a28-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a28-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="b4a28-108">[out] 반환된 이름을 저장하는 문자 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4a28-108">[out] A character array that stores the returned name.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b4a28-109">주의</span><span class="sxs-lookup"><span data-stu-id="b4a28-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="b4a28-110">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4a28-110">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4a28-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4a28-111">Requirements</span></span>  
 <span data-ttu-id="b4a28-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4a28-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4a28-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="b4a28-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="b4a28-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="b4a28-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="b4a28-115">**.NET Framework 버전:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4a28-115">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4a28-116">참조</span><span class="sxs-lookup"><span data-stu-id="b4a28-116">See also</span></span>

- [<span data-ttu-id="b4a28-117">ICorDebugInstanceFieldSymbol 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4a28-117">ICorDebugInstanceFieldSymbol Interface</span></span>](icordebuginstancefieldsymbol-interface.md)
- [<span data-ttu-id="b4a28-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4a28-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
