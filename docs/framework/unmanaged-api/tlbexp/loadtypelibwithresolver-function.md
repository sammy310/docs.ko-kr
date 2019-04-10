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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5c14080e3ac128a6a7fbb48586f59d8a5ea4105f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59155664"
---
# <a name="loadtypelibwithresolver-function"></a><span data-ttu-id="01711-102">LoadTypeLibWithResolver 함수</span><span class="sxs-lookup"><span data-stu-id="01711-102">LoadTypeLibWithResolver Function</span></span>
<span data-ttu-id="01711-103">형식 라이브러리를 로드 하 고 제공 된 사용 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 내부적으로 참조 된 형식 라이브러리를 해결 하려면.</span><span class="sxs-lookup"><span data-stu-id="01711-103">Loads a type library and uses the supplied [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) to resolve any internally referenced type libraries.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="01711-104">구문</span><span class="sxs-lookup"><span data-stu-id="01711-104">Syntax</span></span>  
  
```  
HRESULT LoadTypeLibWithResolver(  
    [in]  LPCOLESTR           szFile,  
    [in]  REGKIND             regkind,  
    [in]  ITypeLibResolver   *pTlbResolver,  
    [out] ITypeLib          **pptlib);  
```  
  
## <a name="parameters"></a><span data-ttu-id="01711-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="01711-105">Parameters</span></span>  
 `szFile`  
 <span data-ttu-id="01711-106">[in] 형식 라이브러리의 파일 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-106">[in] The file path of the type library.</span></span>  
  
 `regkind`  
 <span data-ttu-id="01711-107">[in] A [REGKIND 열거형](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) 형식 라이브러리를 등록 하는 방법을 제어 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-107">[in] A [REGKIND enumeration](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/ne-oleauto-tagregkind) flag that controls how the type library is registered.</span></span> <span data-ttu-id="01711-108">가능한 값은:</span><span class="sxs-lookup"><span data-stu-id="01711-108">Its possible values are:</span></span>  
  
-   `REGKIND_DEFAULT`<span data-ttu-id="01711-109">: 기본 등록 동작을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-109">: Use default registration behavior.</span></span>  
  
-   `REGKIND_REGISTER`<span data-ttu-id="01711-110">: 이 형식 라이브러리를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-110">: Register this type library.</span></span>  
  
-   `REGKIND_NONE`<span data-ttu-id="01711-111">: 이 형식 라이브러리를 등록 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="01711-111">: Do not register this type library.</span></span>  
  
 `pTlbResolver`  
 <span data-ttu-id="01711-112">[in] 구현에 대 한 포인터를 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-112">[in] A pointer to the implementation of the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md).</span></span>  
  
 `pptlib`  
 <span data-ttu-id="01711-113">[out] 로드 되는 형식 라이브러리에 대 한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-113">[out] A reference to the type library that is being loaded.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="01711-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="01711-114">Return Value</span></span>  
 <span data-ttu-id="01711-115">다음 표에 나열 된 HRESULT 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-115">One of the HRESULT values listed in the following table.</span></span>  
  
|<span data-ttu-id="01711-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="01711-116">Return value</span></span>|<span data-ttu-id="01711-117">의미</span><span class="sxs-lookup"><span data-stu-id="01711-117">Meaning</span></span>|  
|------------------|-------------|  
|`S_OK`|<span data-ttu-id="01711-118">명령 실행 성공</span><span class="sxs-lookup"><span data-stu-id="01711-118">Success.</span></span>|  
|`E_OUTOFMEMORY`|<span data-ttu-id="01711-119">메모리가 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-119">Out of memory.</span></span>|  
|`E_POINTER`|<span data-ttu-id="01711-120">포인터 중 하나 이상이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01711-120">One or more of the pointers are invalid.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="01711-121">인수 중 하나 이상이 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="01711-121">One or more of the arguments are invalid.</span></span>|  
|`TYPE_E_IOERROR`|<span data-ttu-id="01711-122">함수는 파일에 쓰지 못했습니다.</span><span class="sxs-lookup"><span data-stu-id="01711-122">The function could not write to the file.</span></span>|  
|`TYPE_E_REGISTRYACCESS`|<span data-ttu-id="01711-123">시스템 등록 데이터베이스를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01711-123">The system registration database could not be opened.</span></span>|  
|`TYPE_E_INVALIDSTATE`|<span data-ttu-id="01711-124">형식 라이브러리를 열 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01711-124">The type library could not be opened.</span></span>|  
|`TYPE_E_CANTLOADLIBRARY`|<span data-ttu-id="01711-125">형식 라이브러리를 DLL을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="01711-125">The type library or DLL could not be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="01711-126">설명</span><span class="sxs-lookup"><span data-stu-id="01711-126">Remarks</span></span>  
 <span data-ttu-id="01711-127">합니다 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) 호출을 `LoadTypeLibWithResolver` 어셈블리를 형식 라이브러리로 변환 하는 동안 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-127">The [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) calls the `LoadTypeLibWithResolver` function during the assembly-to-type-library conversion process.</span></span>  
  
 <span data-ttu-id="01711-128">이 함수는 레지스트리에 대 한 최소한의 액세스를 사용 하 여 지정 된 형식 라이브러리를 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-128">This function loads the specified type library with minimal access to the registry.</span></span> <span data-ttu-id="01711-129">함수는 다음 내부적으로 참조 된 형식 라이브러리를 로드 및 부모 형식 라이브러리에 추가 해야 합니다는 각각에 대 한 형식 라이브러리를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-129">The function then examines the type library for internally referenced type libraries, each of which must be loaded and added to the parent type library.</span></span>  
  
 <span data-ttu-id="01711-130">참조 된 형식 라이브러리를 로드 하기 전에 해당 참조 파일 경로 전체 파일 경로를 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-130">Before a referenced type library can be loaded, its reference file path must be resolved to a full file path.</span></span> <span data-ttu-id="01711-131">이 통해 이루어집니다를 [ResolveTypeLib 메서드](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) 가 제공 하는 합니다 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md)에 전달 되는 `pTlbResolver` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-131">This is accomplished through the [ResolveTypeLib method](../../../../docs/framework/unmanaged-api/tlbexp/resolvetypelib-method.md) that is provided by the [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md), which is passed in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="01711-132">참조 된 형식 라이브러리의 전체 파일 경로, 알려진 경우는 `LoadTypeLibWithResolver` 함수 로드 하 고 결합 된 마스터 형식 라이브러리를 만들고 부모 형식 라이브러리에 참조 된 형식 라이브러리를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-132">When the full file path of the referenced type library is known, the `LoadTypeLibWithResolver` function loads and adds the referenced type library to the parent type library, creating a combined master type library.</span></span>  
  
 <span data-ttu-id="01711-133">함수를 확인 하 고 모든 내부적으로 참조 된 형식 라이브러리를 로드 한 후 마스터 확인 된 형식 라이브러리에 대 한 참조를 반환 합니다는 `pptlib` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-133">After the function resolves and loads all internally referenced type libraries, it returns a reference to the master resolved type library in the `pptlib` parameter.</span></span>  
  
 <span data-ttu-id="01711-134">`LoadTypeLibWithResolver` 함수는 일반적으로 호출한 합니다 [Tlbexp.exe (형식 라이브러리 내보내기)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md)를 제공 하는 자체 내부 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 구현에는 `pTlbResolver` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="01711-134">The `LoadTypeLibWithResolver` function is generally called by the [Tlbexp.exe (Type Library Exporter)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md), which supplies its own internal [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation in the `pTlbResolver` parameter.</span></span>  
  
 <span data-ttu-id="01711-135">호출 하는 경우 `LoadTypeLibWithResolver` 를 직접 제공 해야 사용자 고유의 [ITypeLibResolver 인터페이스](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="01711-135">If you call `LoadTypeLibWithResolver` directly, you must supply your own [ITypeLibResolver interface](../../../../docs/framework/unmanaged-api/tlbexp/itypelibresolver-interface.md) implementation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="01711-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="01711-136">Requirements</span></span>  
 <span data-ttu-id="01711-137">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="01711-137">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="01711-138">**헤더:** TlbRef.h</span><span class="sxs-lookup"><span data-stu-id="01711-138">**Header:** TlbRef.h</span></span>  
  
 <span data-ttu-id="01711-139">**라이브러리:** TlbRef.lib</span><span class="sxs-lookup"><span data-stu-id="01711-139">**Library:** TlbRef.lib</span></span>  
  
 <span data-ttu-id="01711-140">**.NET framework 버전:** 3.5, 3.0, 2.0</span><span class="sxs-lookup"><span data-stu-id="01711-140">**.NET Framework Version:** 3.5, 3.0, 2.0</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01711-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="01711-141">See also</span></span>

- [<span data-ttu-id="01711-142">Tlbexp 도우미 함수</span><span class="sxs-lookup"><span data-stu-id="01711-142">Tlbexp Helper Functions</span></span>](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [<span data-ttu-id="01711-143">LoadTypeLibEx 함수</span><span class="sxs-lookup"><span data-stu-id="01711-143">LoadTypeLibEx Function</span></span>](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
