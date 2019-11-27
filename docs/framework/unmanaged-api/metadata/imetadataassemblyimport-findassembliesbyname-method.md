---
title: IMetaDataAssemblyImport::FindAssembliesByName 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.FindAssembliesByName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::FindAssembliesByName
helpviewer_keywords:
- FindAssembliesByName method [.NET Framework metadata]
- IMetaDataAssemblyImport::FindAssembliesByName method [.NET Framework metadata]
ms.assetid: 4db97cf9-e4c1-4233-8efa-cbdc0e14a8e4
topic_type:
- apiref
ms.openlocfilehash: c12d3a7a7d1e52529435361aa12e22e4edeecf03
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448299"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="79df1-102">IMetaDataAssemblyImport::FindAssembliesByName 메서드</span><span class="sxs-lookup"><span data-stu-id="79df1-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="79df1-103">참조를 확인 하기 위해 CLR (공용 언어 런타임)에서 사용 하는 표준 규칙을 사용 하 여, 지정 된 `szAssemblyName` 매개 변수를 사용 하는 어셈블리의 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="79df1-104">구문</span><span class="sxs-lookup"><span data-stu-id="79df1-104">Syntax</span></span>  
  
```cpp  
HRESULT FindAssembliesByName (  
    [in]  LPCWSTR     szAppBase,   
    [in]  LPCWSTR     szPrivateBin,   
    [in]  LPCWSTR     szAssemblyName,   
    [out] IUnknown    *ppIUnk[],   
    [in]  ULONG       cMax,   
    [out] ULONG       *pcAssemblies  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79df1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79df1-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="79df1-106">진행 지정 된 어셈블리를 검색할 루트 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="79df1-107">이 값이 `null`로 설정 된 경우 `FindAssembliesByName`는 어셈블리에 대 한 전역 어셈블리 캐시만 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="79df1-108">진행 루트 디렉터리 아래에서 어셈블리를 검색할 세미콜론으로 구분 된 하위 디렉터리 (예: "bin; bin2")의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="79df1-109">이러한 디렉터리는 기본 검색 규칙에 지정 된 디렉터리 외에도 검색 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="79df1-110">진행 찾을 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="79df1-111">이 문자열의 형식은 <xref:System.Reflection.AssemblyName>의 클래스 참조 페이지에서 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="79df1-112">진행 `IMetadataAssemblyImport` 인터페이스 포인터를 넣을 [IUnknown](/cpp/atl/iunknown) 형식의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="79df1-113">제한이 `ppIUnk`에 배치할 수 있는 인터페이스 포인터의 최대 수입니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="79df1-114">제한이 반환 된 인터페이스 포인터의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="79df1-115">즉, `ppIUnk`에 실제로 배치 된 인터페이스 포인터의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79df1-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="79df1-116">Return Value</span></span>  
  
|<span data-ttu-id="79df1-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79df1-117">HRESULT</span></span>|<span data-ttu-id="79df1-118">설명</span><span class="sxs-lookup"><span data-stu-id="79df1-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="79df1-119">`FindAssembliesByName` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="79df1-120">어셈블리가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="79df1-121">설명</span><span class="sxs-lookup"><span data-stu-id="79df1-121">Remarks</span></span>  
 <span data-ttu-id="79df1-122">어셈블리 이름이 지정 된 경우 `FindAssembliesByName` 메서드는 어셈블리 참조를 확인 하는 표준 규칙에 따라 어셈블리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="79df1-123">(자세한 내용은 [런타임에서 어셈블리를 찾는 방법](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)을 참조 하세요.) `FindAssembliesByName`를 사용 하 여 호출자는 응용 프로그램 기본 및 개인 검색 경로와 같은 어셈블리 확인 프로그램 컨텍스트의 다양 한 측면을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="79df1-124">`FindAssembliesByName` 메서드를 사용 하려면 어셈블리 확인 논리를 호출 하기 위해 프로세스에서 CLR을 초기화 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="79df1-125">따라서 `FindAssembliesByName`를 호출 하기 전에 [Coinitializeee](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (COINITEE_DEFAULT 전달)를 호출한 다음 [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)에 대 한 호출을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="79df1-126">`FindAssembliesByName`은 전달 된 어셈블리 이름에 대 한 어셈블리 매니페스트가 포함 된 파일에 대 한 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 포인터를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="79df1-127">지정 된 어셈블리 이름이 완전히 지정 되지 않은 경우 (예: 버전을 포함 하지 않는 경우) 여러 어셈블리가 반환 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="79df1-128">`FindAssembliesByName`는 컴파일 시간에 참조 된 어셈블리를 찾으려고 시도 하는 컴파일러에서 일반적으로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="79df1-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79df1-129">Requirements</span></span>  
 <span data-ttu-id="79df1-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79df1-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79df1-131">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="79df1-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79df1-132">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="79df1-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79df1-133">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79df1-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79df1-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="79df1-134">See also</span></span>

- [<span data-ttu-id="79df1-135">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="79df1-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="79df1-136">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79df1-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
