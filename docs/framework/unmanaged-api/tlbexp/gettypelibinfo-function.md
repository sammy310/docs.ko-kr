---
title: GetTypeLibInfo 함수
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d12cbb66464baba4ee706ccb076764fbf025fc5f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786180"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="d372f-102">GetTypeLibInfo 함수</span><span class="sxs-lookup"><span data-stu-id="d372f-102">GetTypeLibInfo Function</span></span>
<span data-ttu-id="d372f-103">검사 하 여 지정된 된 형식 라이브러리에 대 한 정보를 반환 합니다. 해당 [>TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-103">Returns information about the specified type library by examining its [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d372f-104">구문</span><span class="sxs-lookup"><span data-stu-id="d372f-104">Syntax</span></span>  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d372f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d372f-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="d372f-106">[in] 형식 라이브러리의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-106">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="d372f-107">[out] 형식 라이브러리의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-107">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="d372f-108">[out] 지역화 ID 형식 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-108">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="d372f-109">[out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) 형식 라이브러리에 대 한 대상 운영 체제를 식별 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-109">[out] A [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="d372f-110">일반적인 값은 SYS_WIN32 SYS_WIN64입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-110">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="d372f-111">[out] 형식 라이브러리의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-111">[out] The major version number of the type library.</span></span> <span data-ttu-id="d372f-112">예를 들어 버전용 *x.y*, 주 버전 번호는 *x*합니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-112">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="d372f-113">[out] 형식 라이브러리의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-113">[out] The minor version number of the type library.</span></span> <span data-ttu-id="d372f-114">버전에 대 한 예를 들어 *x.y*, 부 버전 번호가 *y*합니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-114">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d372f-115">설명</span><span class="sxs-lookup"><span data-stu-id="d372f-115">Remarks</span></span>  
 <span data-ttu-id="d372f-116">합니다 `GetTypeLibInfo` 의해 함수가 호출 되는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-116">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="d372f-117">이 도구는 공용 언어 런타임 (CLR) 어셈블리에서 형식을 설명 하는 형식 라이브러리를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-117">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="d372f-118">함수를 반환 하는 경우 모든 매개 변수를는 `HRESULT` 의 `E_POINTER`합니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-118">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="d372f-119">그 외의 경우 `S_OK`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d372f-119">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d372f-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d372f-120">Requirements</span></span>  
 <span data-ttu-id="d372f-121">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d372f-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d372f-122">**헤더:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="d372f-122">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="d372f-123">**라이브러리:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="d372f-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="d372f-124">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d372f-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d372f-125">참고자료</span><span class="sxs-lookup"><span data-stu-id="d372f-125">See also</span></span>

- [<span data-ttu-id="d372f-126">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="d372f-126">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="d372f-127">LoadTypeLibEx 함수</span><span class="sxs-lookup"><span data-stu-id="d372f-127">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
