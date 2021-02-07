---
description: '자세히 알아보기: ICorDebugDataTarget2:: Geation Agelocation 메서드'
title: ICorDebugDataTarget2::GetImageLocation 메서드
ms.date: 03/30/2017
ms.assetid: 696afe71-5852-478d-a33f-b2d2dbc4b91f
ms.openlocfilehash: f79ba89d3ba467c2e81224d64147c2b5dd5db079
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99710493"
---
# <a name="icordebugdatatarget2getimagelocation-method"></a><span data-ttu-id="bf37b-103">ICorDebugDataTarget2::GetImageLocation 메서드</span><span class="sxs-lookup"><span data-stu-id="bf37b-103">ICorDebugDataTarget2::GetImageLocation Method</span></span>

<span data-ttu-id="bf37b-104">모듈의 경로를 모듈의 기준 주소에서 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bf37b-104">Returns the path of a module from the module's base address.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bf37b-105">구문</span><span class="sxs-lookup"><span data-stu-id="bf37b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetImageLocation(    [in] CORDB_ADDRESS baseAddress,  
    [in] ULONG32 cchName,  
    [out] ULONG32 *pcchName,  
    [out, size_is(cchName), length_is(*pcchName)] WCHAR szName[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bf37b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bf37b-106">Parameters</span></span>  

 `baseAddress`  
 <span data-ttu-id="bf37b-107">진행 모듈의 기준 주소를 나타내는 [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="bf37b-107">[in] A [CORDB_ADDRESS](../common-data-types-unmanaged-api-reference.md) value that represents the module's base address.</span></span>  
  
 `cchName`  
 <span data-ttu-id="bf37b-108">[in] 모듈 경로를 수신할 버퍼의 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bf37b-108">[in] The number of characters in the buffer that is to receive the module path.</span></span>  
  
 `pcchName`  
 <span data-ttu-id="bf37b-109">[out] `szName` 버퍼에 기록된 문자 수에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="bf37b-109">[out] A pointer to the number of characters written to the `szName` buffer.</span></span>  
  
 `szName`  
 <span data-ttu-id="bf37b-110">[out] 모듈의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="bf37b-110">[out] The path of the module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bf37b-111">설명</span><span class="sxs-lookup"><span data-stu-id="bf37b-111">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="bf37b-112">이 메서드는 .NET 네이티브에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf37b-112">This method is available with .NET Native only.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bf37b-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf37b-113">Requirements</span></span>  

 <span data-ttu-id="bf37b-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bf37b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bf37b-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="bf37b-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="bf37b-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="bf37b-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="bf37b-117">**.NET Framework 버전:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bf37b-117">**.NET Framework Versions:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bf37b-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bf37b-118">See also</span></span>

- [<span data-ttu-id="bf37b-119">ICorDebugDataTarget2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf37b-119">ICorDebugDataTarget2 Interface</span></span>](icordebugdatatarget2-interface.md)
- [<span data-ttu-id="bf37b-120">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bf37b-120">Debugging Interfaces</span></span>](debugging-interfaces.md)
