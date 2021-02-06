---
description: '자세히 알아보기: ICorDebugMergedAssemblyRecord:: GetSimpleName 메서드'
title: ICorDebugMergedAssemblyRecord::GetSimpleName 메서드
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
ms.openlocfilehash: e77a5cc7df009a5bc55a7eb952ead80e5f81f271
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650393"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="05b84-103">ICorDebugMergedAssemblyRecord::GetSimpleName 메서드</span><span class="sxs-lookup"><span data-stu-id="05b84-103">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>

<span data-ttu-id="05b84-104">어셈블리의 단순한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-104">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="05b84-105">구문</span><span class="sxs-lookup"><span data-stu-id="05b84-105">Syntax</span></span>  
  
```cpp  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,
   [out] ULONG32 *pcchName,
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="05b84-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="05b84-106">Parameters</span></span>  

 `cchName`  
 <span data-ttu-id="05b84-107">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-107">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="05b84-108">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-108">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="05b84-109">문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-109">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="05b84-110">설명</span><span class="sxs-lookup"><span data-stu-id="05b84-110">Remarks</span></span>  

 <span data-ttu-id="05b84-111">이 메서드는 파일 확장명, 버전, 문화권 또는 공개 키 토큰 없이 어셈블리의 단순한 이름(예: "System.Collections")을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-111">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="05b84-112">관리 코드의 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-112">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="05b84-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="05b84-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="05b84-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="05b84-114">Requirements</span></span>  

 <span data-ttu-id="05b84-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="05b84-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="05b84-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="05b84-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="05b84-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="05b84-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="05b84-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="05b84-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="05b84-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="05b84-119">See also</span></span>

- [<span data-ttu-id="05b84-120">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05b84-120">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="05b84-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="05b84-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
