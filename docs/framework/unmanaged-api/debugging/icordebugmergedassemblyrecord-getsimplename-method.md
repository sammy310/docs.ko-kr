---
title: ICorDebugMergedAssemblyRecord::GetSimpleName 메서드
ms.date: 03/30/2017
ms.assetid: bc3410f6-ebca-4bca-9b45-fc38c74fa9cb
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: df142ea8f02d5cefc5c63a2d376afb331b4379ce
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59197986"
---
# <a name="icordebugmergedassemblyrecordgetsimplename-method"></a><span data-ttu-id="f95e5-102">ICorDebugMergedAssemblyRecord::GetSimpleName 메서드</span><span class="sxs-lookup"><span data-stu-id="f95e5-102">ICorDebugMergedAssemblyRecord::GetSimpleName Method</span></span>
<span data-ttu-id="f95e5-103">어셈블리의 단순한 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f95e5-103">Gets the simple name of the assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f95e5-104">구문</span><span class="sxs-lookup"><span data-stu-id="f95e5-104">Syntax</span></span>  
  
```  
HRESULT GetSimpleName(  
   [in] ULONG32 cchName,   
   [out] ULONG32 *pcchName,   
   [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f95e5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f95e5-105">Parameters</span></span>  
 `cchName`  
 <span data-ttu-id="f95e5-106">[in] `szName` 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f95e5-106">[in] The number of characters in the `szName` buffer.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="f95e5-107">[out] `szName` 버퍼에 실제로 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f95e5-107">[out] A pointer to the number of characters actually written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="f95e5-108">문자 배열에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f95e5-108">A pointer to a character array.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f95e5-109">설명</span><span class="sxs-lookup"><span data-stu-id="f95e5-109">Remarks</span></span>  
 <span data-ttu-id="f95e5-110">이 메서드는 파일 확장명, 버전, 문화권 또는 공개 키 토큰 없이 어셈블리의 단순한 이름(예: "System.Collections")을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f95e5-110">This method retrieves the simple name of an assembly (such as "System.Collections"), without a file extension, version, culture, or public key token.</span></span> <span data-ttu-id="f95e5-111">관리 코드의 <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> 속성에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="f95e5-111">It corresponds to the <xref:System.Reflection.AssemblyName.Name%2A?displayProperty=nameWithType> property in managed code.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f95e5-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f95e5-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f95e5-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f95e5-113">Requirements</span></span>  
 <span data-ttu-id="f95e5-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f95e5-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f95e5-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f95e5-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f95e5-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f95e5-116">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="f95e5-117">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="f95e5-117">.NET Framework Versions:</span></span>** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="f95e5-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="f95e5-118">See also</span></span>

- [<span data-ttu-id="f95e5-119">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f95e5-119">ICorDebugMergedAssemblyRecord Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="f95e5-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f95e5-120">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
