---
description: '자세히 알아보기: GetTypeLibInfo 함수'
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
ms.openlocfilehash: 61a830f3ce81345634da377f6fc815a307700e9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99794470"
---
# <a name="gettypelibinfo-function"></a><span data-ttu-id="ec4fe-103">GetTypeLibInfo 함수</span><span class="sxs-lookup"><span data-stu-id="ec4fe-103">GetTypeLibInfo Function</span></span>

<span data-ttu-id="ec4fe-104">[TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) 구조를 시험하여 지정된 형식 라이브러리에 대한 정보를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-104">Returns information about the specified type library by examining its [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ec4fe-105">구문</span><span class="sxs-lookup"><span data-stu-id="ec4fe-105">Syntax</span></span>  
  
```cpp  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ec4fe-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ec4fe-106">Parameters</span></span>  

 `szFile`  
 <span data-ttu-id="ec4fe-107">진행 형식 라이브러리의 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-107">[in] The file name of the type library.</span></span>  
  
 `pTypeLibID`  
 <span data-ttu-id="ec4fe-108">제한이 형식 라이브러리의 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-108">[out] The GUID of the type library.</span></span>  
  
 `pTypeLibLCID`  
 <span data-ttu-id="ec4fe-109">제한이 형식 라이브러리의 지역화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-109">[out] The localization ID of the type library.</span></span>  
  
 `pTypeLibPlatform`  
 <span data-ttu-id="ec4fe-110">제한이 형식 라이브러리의 대상 운영 체제를 식별 하는 [syskind](/windows/win32/api/oaidl/ne-oaidl-syskind) 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-110">[out] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the target operating system for the type library.</span></span> <span data-ttu-id="ec4fe-111">공통 값은 SYS_WIN32 및 SYS_WIN64입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-111">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pTypeLibMajorVer`  
 <span data-ttu-id="ec4fe-112">제한이 형식 라이브러리의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-112">[out] The major version number of the type library.</span></span> <span data-ttu-id="ec4fe-113">예를 들어 버전 *x. y* 의 경우 주 버전 번호는 *x* 입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-113">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `pTypeLibMinorVer`  
 <span data-ttu-id="ec4fe-114">제한이 형식 라이브러리의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-114">[out] The minor version number of the type library.</span></span> <span data-ttu-id="ec4fe-115">예를 들어 버전 *x. y* 의 경우 부 버전 번호는 *y* 입니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-115">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ec4fe-116">설명</span><span class="sxs-lookup"><span data-stu-id="ec4fe-116">Remarks</span></span>  

 <span data-ttu-id="ec4fe-117">`GetTypeLibInfo`함수는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../tools/tlbexp-exe-type-library-exporter.md)에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-117">The `GetTypeLibInfo` function is called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md).</span></span> <span data-ttu-id="ec4fe-118">이 도구는 CLR (공용 언어 런타임) 어셈블리의 형식을 설명 하는 형식 라이브러리를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-118">This tool generates a type library that describes the types in a common language runtime (CLR) assembly.</span></span>  
  
 <span data-ttu-id="ec4fe-119">매개 변수가 null 인 경우이 함수는의를 반환 합니다 `HRESULT` `E_POINTER` .</span><span class="sxs-lookup"><span data-stu-id="ec4fe-119">If any parameter is null, the function returns an `HRESULT` of `E_POINTER`.</span></span> <span data-ttu-id="ec4fe-120">그렇지 않으면 `S_OK`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-120">Otherwise, it returns `S_OK`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ec4fe-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ec4fe-121">Requirements</span></span>  

 <span data-ttu-id="ec4fe-122">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ec4fe-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ec4fe-123">**헤더:** TlbRef</span><span class="sxs-lookup"><span data-stu-id="ec4fe-123">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="ec4fe-124">**라이브러리:** TlbRef</span><span class="sxs-lookup"><span data-stu-id="ec4fe-124">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="ec4fe-125">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec4fe-125">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ec4fe-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ec4fe-126">See also</span></span>

- [<span data-ttu-id="ec4fe-127">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="ec4fe-127">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="ec4fe-128">LoadTypeLibEx 함수</span><span class="sxs-lookup"><span data-stu-id="ec4fe-128">LoadTypeLibEx Function</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
