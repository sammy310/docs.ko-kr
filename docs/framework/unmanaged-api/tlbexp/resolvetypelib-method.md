---
description: '자세히 알아보기: ResolveTypeLib 메서드'
title: ResolveTypeLib 메서드
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
ms.openlocfilehash: ca7f94f630479d30bb9129497b38bcf04e759e5d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99646285"
---
# <a name="resolvetypelib-method"></a><span data-ttu-id="d23db-103">ResolveTypeLib 메서드</span><span class="sxs-lookup"><span data-stu-id="d23db-103">ResolveTypeLib Method</span></span>

<span data-ttu-id="d23db-104">정규화 된 경로를 반환 하 여 형식 라이브러리의 단순 이름을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-104">Resolves the simple name of a type library by returning its fully qualified path.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d23db-105">구문</span><span class="sxs-lookup"><span data-stu-id="d23db-105">Syntax</span></span>  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d23db-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d23db-106">Parameters</span></span>  

 `bstrSimpleName`  
 <span data-ttu-id="d23db-107">진행 형식 라이브러리의 단순한 이름을 포함 하는 [BSTR](/previous-versions/windows/desktop/automat/bstr) 입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-107">[in] A [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the simple name of the type library.</span></span>  
  
 `tlbid`  
 <span data-ttu-id="d23db-108">진행 레지스트리의 형식 라이브러리에 할당 된 GUID입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-108">[in] The GUID assigned to the type library in the registry.</span></span>  
  
 `lcid`  
 <span data-ttu-id="d23db-109">진행 형식 라이브러리의 지역화 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-109">[in] The localization ID of the type library.</span></span>  
  
 `wMajorVersion`  
 <span data-ttu-id="d23db-110">진행 형식 라이브러리의 주 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-110">[in] The major version number of the type library.</span></span> <span data-ttu-id="d23db-111">예를 들어 버전 *x. y* 의 경우 주 버전 번호는 *x* 입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-111">For example, for version *x.y*, the major version number is *x*.</span></span>  
  
 `wMinorVersion`  
 <span data-ttu-id="d23db-112">진행 형식 라이브러리의 부 버전 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-112">[in] The minor version number of the type library.</span></span> <span data-ttu-id="d23db-113">예를 들어 버전 *x. y* 의 경우 부 버전 번호는 *y* 입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-113">For example, for version *x.y*, the minor version number is *y*.</span></span>  
  
 `syskind`  
 <span data-ttu-id="d23db-114">진행 운영 환경을 식별 하는 [Syskind](/windows/win32/api/oaidl/ne-oaidl-syskind) 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-114">[in] A [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) flag that identifies the operating environment.</span></span> <span data-ttu-id="d23db-115">공통 값은 SYS_WIN32 및 SYS_WIN64입니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-115">Common values are SYS_WIN32 and SYS_WIN64.</span></span>  
  
 `pbstrResolvedTlbName`  
 <span data-ttu-id="d23db-116">제한이 매개 변수에 이름이 지정 된 형식 라이브러리의 전체 경로를 포함 하는 [BSTR](/previous-versions/windows/desktop/automat/bstr) 에 대 한 포인터입니다 `bstrSimpleName` .</span><span class="sxs-lookup"><span data-stu-id="d23db-116">[out] A pointer to a [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d23db-117">설명</span><span class="sxs-lookup"><span data-stu-id="d23db-117">Remarks</span></span>  

 <span data-ttu-id="d23db-118">`ResolveTypeLib`메서드는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../tools/tlbexp-exe-type-library-exporter.md) 를 처리 하는 동안 [LoadTypeLibWithResolver 함수](loadtypelibwithresolver-function.md) 에서 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d23db-118">The `ResolveTypeLib` method is called by the [LoadTypeLibWithResolver function](loadtypelibwithresolver-function.md) during [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) processing.</span></span>  
  
 <span data-ttu-id="d23db-119">이 인터페이스의 사용자 지정 구현은 매개 변수에서 이름이 인 형식 라이브러리의 전체 경로를 포함 하는 [BSTR](/previous-versions/windows/desktop/automat/bstr) 을 반환 해야 합니다 `bstrSimpleName` .</span><span class="sxs-lookup"><span data-stu-id="d23db-119">Custom implementations of this interface must return a [BSTR](/previous-versions/windows/desktop/automat/bstr) that contains the full path of the type library named in the `bstrSimpleName` parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d23db-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d23db-120">Requirements</span></span>  

 <span data-ttu-id="d23db-121">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d23db-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d23db-122">**헤더:** TlbRef, TlbRef</span><span class="sxs-lookup"><span data-stu-id="d23db-122">**Header:** TlbRef.idl, TlbRef.h</span></span>  
  
 <span data-ttu-id="d23db-123">**라이브러리:** TlbRef</span><span class="sxs-lookup"><span data-stu-id="d23db-123">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="d23db-124">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d23db-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d23db-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d23db-125">See also</span></span>

- [<span data-ttu-id="d23db-126">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="d23db-126">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="d23db-127">LoadTypeLibEx</span><span class="sxs-lookup"><span data-stu-id="d23db-127">LoadTypeLibEx</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
