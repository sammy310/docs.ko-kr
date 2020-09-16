---
title: LoadTypeLibWithResolver 함수
ms.date: 03/30/2017
api_name:
- LoadTypeLibWithResolver
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- LoadTypeLibWithResolver
helpviewer_keywords:
- LoadTypeLibWithResolver function [.NET Framework]
ms.assetid: 7123a89b-eb9b-463a-a552-a081e33b0a3a
topic_type:
- apiref
ms.openlocfilehash: 395d5f63eef12570c07f1f601de7f9e480d62905
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540507"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="55383-102">LoadTypeLibWithResolver 함수</span><span class="sxs-lookup"><span data-stu-id="55383-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="55383-103">형식 라이브러리를 로드 하 고 제공 된 [ITypeLibResolver 인터페이스](itypelibresolver-interface.md) 를 사용 하 여 내부적으로 참조 되는 형식 라이브러리를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-103">Loads a type library and uses the supplied [ITypeLibResolver interface](itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="55383-104">구문</span><span class="sxs-lookup"><span data-stu-id="55383-104">Syntax</span></span>  
  
```cpp  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="55383-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="55383-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="55383-106">진행 형식 라이브러리의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="55383-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="55383-107">진행 형식 라이브러리를 등록 하는 방법을 제어 하는 [Regkind 열거형](/windows/win32/api/oleauto/ne-oleauto-regkind) 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="55383-107">[in] A [REGKIND enumeration](/windows/win32/api/oleauto/ne-oleauto-regkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="55383-108">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="55383-108">Its possible values are:</span></span>  
  
- <span data-ttu-id="55383-109">`REGKIND_DEFAULT`: 기본 등록 동작을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-109">`REGKIND_DEFAULT`: Use default registration behavior.</span></span>  
  
- <span data-ttu-id="55383-110">`REGKIND_REGISTER`:이 형식 라이브러리를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-110">`REGKIND_REGISTER`: Register this type library.</span></span>  
  
- <span data-ttu-id="55383-111">`REGKIND_NONE`:이 형식 라이브러리를 등록 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="55383-111">`REGKIND_NONE`: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="55383-112">진행 [ITypeLibResolver 인터페이스](itypelibresolver-interface.md)의 구현에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="55383-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="55383-113">제한이 로드 되 고 있는 형식 라이브러리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="55383-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="55383-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="55383-114">Return Value</span></span>  
 <span data-ttu-id="55383-115">다음 표에 나열 된 HRESULT 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="55383-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="55383-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="55383-116">Return value</span></span>|<span data-ttu-id="55383-117">의미</span><span class="sxs-lookup"><span data-stu-id="55383-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="55383-118">성공.</span><span class="sxs-lookup"><span data-stu-id="55383-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="55383-119">메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="55383-120">하나 이상의 포인터가 잘못 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55383-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="55383-121">하나 이상의 인수가 잘못되었습니다.</span><span class="sxs-lookup"><span data-stu-id="55383-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="55383-122">함수에서 파일에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55383-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="55383-123">시스템 등록 데이터베이스를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55383-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="55383-124">형식 라이브러리를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55383-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="55383-125">형식 라이브러리 또는 DLL을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="55383-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="55383-126">설명</span><span class="sxs-lookup"><span data-stu-id="55383-126">Remarks</span></span>  
 <span data-ttu-id="55383-127">[Tlbexp.exe (형식 라이브러리 내보내기)](../../tools/tlbexp-exe-type-library-exporter.md) 는 어셈블리에서 `LoadTypeLibWithResolver` 형식 라이브러리로의 변환 프로세스 중에 함수를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-127">The [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="55383-128">이 함수는 레지스트리에 대 한 최소 액세스 권한으로 지정 된 형식 라이브러리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="55383-129">그런 다음 함수는 내부적으로 참조 되는 형식 라이브러리에 대 한 형식 라이브러리를 검사 합니다. 각 라이브러리는 로드 되어 부모 형식 라이브러리에 추가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="55383-130">참조 된 형식 라이브러리를 로드 하려면 먼저 해당 참조 파일 경로를 전체 파일 경로로 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="55383-131">이는 매개 변수로 전달 되는 [ITypeLibResolver 인터페이스](itypelibresolver-interface.md)에서 제공 하는 [ResolveTypeLib 메서드](resolvetypelib-method.md) 를 통해 수행 됩니다 `pTlbResolver` .</span><span class="sxs-lookup"><span data-stu-id="55383-131">This is accomplished through the [ResolveTypeLib method](resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="55383-132">참조 된 형식 라이브러리의 전체 파일 경로를 알고 있는 경우 함수는 `LoadTypeLibWithResolver` 참조 된 형식 라이브러리를 로드 하 여 부모 형식 라이브러리에 추가 하 고 결합 된 마스터 형식 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55383-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="55383-133">함수가 내부적으로 참조 되는 형식 라이브러리를 모두 확인 하 고 로드 한 후에는 매개 변수에서 마스터의 확인 된 형식 라이브러리에 대 한 참조를 반환 `pptlib` 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="55383-134">`LoadTypeLibWithResolver`함수는 일반적으로 매개 변수에 고유한 내부 [ITypeLibResolver 인터페이스](itypelibresolver-interface.md) 구현을 제공 하는 [Tlbexp.exe (형식 라이브러리 내보내기)](../../tools/tlbexp-exe-type-library-exporter.md)에서 호출 됩니다 `pTlbResolver` .</span><span class="sxs-lookup"><span data-stu-id="55383-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="55383-135">`LoadTypeLibWithResolver`을 직접 호출 하는 경우 고유한 [ITypeLibResolver 인터페이스](itypelibresolver-interface.md) 구현을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="55383-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="55383-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="55383-136">Requirements</span></span>  
 <span data-ttu-id="55383-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55383-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="55383-138">**헤더:** TlbRef</span><span class="sxs-lookup"><span data-stu-id="55383-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="55383-139">**라이브러리:** TlbRef</span><span class="sxs-lookup"><span data-stu-id="55383-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="55383-140">**.NET Framework 버전:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="55383-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="55383-141">참조</span><span class="sxs-lookup"><span data-stu-id="55383-141">See also</span></span>

- [<span data-ttu-id="55383-142">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="55383-142">Tlbexp Helper Functions</span></span>](index.md)
- [<span data-ttu-id="55383-143">LoadTypeLibEx 함수</span><span class="sxs-lookup"><span data-stu-id="55383-143">LoadTypeLibEx Function</span></span>](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
