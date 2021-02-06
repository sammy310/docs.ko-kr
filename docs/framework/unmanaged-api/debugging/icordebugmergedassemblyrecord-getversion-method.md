---
description: '자세히 알아보기: ICorDebugMergedAssemblyRecord:: GetVersion 메서드'
title: ICorDebugMergedAssemblyRecord::GetVersion 메서드
ms.date: 03/30/2017
ms.assetid: c6858b06-ae26-4312-b325-ea6025016675
ms.openlocfilehash: 0e87e2bbb1207ebd1eb5775b7f52d5689b4e8727
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99650341"
---
# <a name="icordebugmergedassemblyrecordgetversion-method"></a><span data-ttu-id="0a374-103">ICorDebugMergedAssemblyRecord::GetVersion 메서드</span><span class="sxs-lookup"><span data-stu-id="0a374-103">ICorDebugMergedAssemblyRecord::GetVersion Method</span></span>

<span data-ttu-id="0a374-104">어셈블리의 버전 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a374-104">Gets the assembly's version information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a374-105">구문</span><span class="sxs-lookup"><span data-stu-id="0a374-105">Syntax</span></span>  
  
```cpp  
HRESULT GetVersion(  
   [out] USHORT *pMajor,
   [out] USHORT *pMinor,
   [out] USHORT *pBuild,
   [out] USHORT *pRevision  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a374-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a374-106">Parameters</span></span>  

 `pMajor`  
 <span data-ttu-id="0a374-107">[out] 주 버전 번호에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a374-107">[out] A pointer to the major version number.</span></span>  
  
 `pMinor`  
 <span data-ttu-id="0a374-108">[out] 부 버전 번호에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a374-108">[out] A pointer to the minor version number.</span></span>  
  
 `pBuild`  
 <span data-ttu-id="0a374-109">[out] 빌드 번호에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a374-109">[out] A pointer to the build number.</span></span>  
  
 `pRevision`  
 <span data-ttu-id="0a374-110">[out] 수정 번호에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0a374-110">[out] A pointer to the revision number.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="0a374-111">설명</span><span class="sxs-lookup"><span data-stu-id="0a374-111">Remarks</span></span>  

 <span data-ttu-id="0a374-112">어셈블리 버전 번호에 대한 자세한 내용은 <xref:System.Version> 클래스 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a374-112">For information on assembly version numbers, see the <xref:System.Version> class topic.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="0a374-113">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a374-113">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a374-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a374-114">Requirements</span></span>  

 <span data-ttu-id="0a374-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0a374-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a374-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="0a374-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="0a374-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="0a374-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="0a374-118">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0a374-118">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a374-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a374-119">See also</span></span>

- [<span data-ttu-id="0a374-120">ICorDebugMergedAssemblyRecord 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a374-120">ICorDebugMergedAssemblyRecord Interface</span></span>](icordebugmergedassemblyrecord-interface.md)
- [<span data-ttu-id="0a374-121">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a374-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
