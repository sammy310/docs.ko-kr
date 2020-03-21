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
ms.openlocfilehash: c0f81e3767d4ea3bc336203fbe8c914b4e2bd07b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177795"
---
# <a name="imetadataassemblyimportfindassembliesbyname-method"></a><span data-ttu-id="667d8-102">IMetaDataAssemblyImport::FindAssembliesByName 메서드</span><span class="sxs-lookup"><span data-stu-id="667d8-102">IMetaDataAssemblyImport::FindAssembliesByName Method</span></span>
<span data-ttu-id="667d8-103">참조를 해결하기 위해 공통 `szAssemblyName` 언어 런타임(CLR)에서 사용하는 표준 규칙을 사용하여 지정된 매개 변수를 사용하여 어셈블리 배열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-103">Gets an array of assemblies with the specified `szAssemblyName` parameter, using the standard rules employed by the common language runtime (CLR) for resolving references.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="667d8-104">구문</span><span class="sxs-lookup"><span data-stu-id="667d8-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="667d8-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="667d8-105">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="667d8-106">【인】 지정된 어셈블리를 검색할 루트 디렉터리입니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-106">[in] The root directory in which to search for the given assembly.</span></span> <span data-ttu-id="667d8-107">이 값을 `null`로 `FindAssembliesByName` 설정된 경우 어셈블리에 대한 전역 어셈블리 캐시에서만 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-107">If this value is set to `null`, `FindAssembliesByName` will look only in the global assembly cache for the assembly.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="667d8-108">【인】 어셈블리를 검색할 루트 디렉터리 아래에 세미콜론으로 구분된 하위 디렉토리(예: "bin;bin2") 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-108">[in] A list of semicolon-delimited subdirectories (for example, "bin;bin2"), under the root directory, in which to search for the assembly.</span></span> <span data-ttu-id="667d8-109">이러한 디렉터리에는 기본 검색 규칙에 지정된 디렉터리 외에 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-109">These directories are probed in addition to those specified in the default probing rules.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="667d8-110">【인】 찾을 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-110">[in] The name of the assembly to find.</span></span> <span data-ttu-id="667d8-111">이 문자열의 형식은 에 대한 <xref:System.Reflection.AssemblyName>클래스 참조 페이지에 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-111">The format of this string is defined in the class reference page for <xref:System.Reflection.AssemblyName>.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="667d8-112">【인】 인터페이스 포인터를 넣을 [IUnknown](/cpp/atl/iunknown) 형식의 `IMetadataAssemblyImport` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-112">[in] An array of type [IUnknown](/cpp/atl/iunknown) in which to put the `IMetadataAssemblyImport` interface pointers.</span></span>  
  
 `cMax`  
 <span data-ttu-id="667d8-113">【아웃】 에 `ppIUnk`배치할 수 있는 최대 인터페이스 포인터 수입니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-113">[out] The maximum number of interface pointers that can be placed in `ppIUnk`.</span></span>  
  
 `pcAssemblies`  
 <span data-ttu-id="667d8-114">【아웃】 반환된 인터페이스 포인터 수입니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-114">[out] The number of interface pointers returned.</span></span> <span data-ttu-id="667d8-115">즉, 실제로 에 배치된 인터페이스 `ppIUnk`포인터의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-115">That is, the number of interface pointers actually placed in `ppIUnk`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="667d8-116">Return Value</span><span class="sxs-lookup"><span data-stu-id="667d8-116">Return Value</span></span>  
  
|<span data-ttu-id="667d8-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="667d8-117">HRESULT</span></span>|<span data-ttu-id="667d8-118">Description</span><span class="sxs-lookup"><span data-stu-id="667d8-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="667d8-119">`FindAssembliesByName`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-119">`FindAssembliesByName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="667d8-120">어셈블리가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-120">There are no assemblies.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="667d8-121">설명</span><span class="sxs-lookup"><span data-stu-id="667d8-121">Remarks</span></span>  
 <span data-ttu-id="667d8-122">어셈블리 이름이 `FindAssembliesByName` 지정되면 메서드는 어셈블리 참조를 해결하기 위한 표준 규칙을 따라 어셈블리를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-122">Given an assembly name, the `FindAssembliesByName` method finds the assembly by following the standard rules for resolving assembly references.</span></span> <span data-ttu-id="667d8-123">자세한 내용은 [런타임이 어셈블리를 찾는 방법을](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)참조하십시오. `FindAssembliesByName` 호출자가 응용 프로그램 기반 및 개인 검색 경로와 같은 어셈블리 확인자 컨텍스트의 다양한 측면을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-123">(For more information, see [How the Runtime Locates Assemblies](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md).) `FindAssembliesByName` allows the caller to configure various aspects of the assembly resolver context, such as application base and private search path.</span></span>  
  
 <span data-ttu-id="667d8-124">이 `FindAssembliesByName` 메서드는 어셈블리 확인 논리를 호출하기 위해 프로세스에서 CLR을 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-124">The `FindAssembliesByName` method requires the CLR to be initialized in the process in order to invoke the assembly resolution logic.</span></span> <span data-ttu-id="667d8-125">따라서 호출하기 `FindAssembliesByName`전에 [CoInitializeEE(COINITEE_DEFAULT](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) 전달)를 호출한 다음 [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md)에 대한 호출을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-125">Therefore, you must call [CoInitializeEE](../../../../docs/framework/unmanaged-api/hosting/coinitializeee-function.md) (passing COINITEE_DEFAULT) before calling `FindAssembliesByName`, and then follow with a call to [CoUninitializeCor](../../../../docs/framework/unmanaged-api/hosting/couninitializecor-function.md).</span></span>  
  
 <span data-ttu-id="667d8-126">`FindAssembliesByName`에서는 전달되는 어셈블리 이름에 대한 어셈블리 매니페스트가 포함된 파일에 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 포인터를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-126">`FindAssembliesByName` returns an [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) pointer to the file containing the assembly manifest for the assembly name that is passed in.</span></span> <span data-ttu-id="667d8-127">지정된 어셈블리 이름이 완전히 지정되지 않은 경우(예: 버전을 포함하지 않는 경우) 여러 어셈블리가 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-127">If the given assembly name is not fully specified (for example, if it does not include a version), multiple assemblies might be returned.</span></span>  
  
 <span data-ttu-id="667d8-128">`FindAssembliesByName`일반적으로 컴파일타임에 참조된 어셈블리를 찾으려고 시도하는 컴파일러에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="667d8-128">`FindAssembliesByName` is commonly used by a compiler that attempts to find a referenced assembly at compile time.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="667d8-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="667d8-129">Requirements</span></span>  
 <span data-ttu-id="667d8-130">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="667d8-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="667d8-131">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="667d8-131">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="667d8-132">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="667d8-132">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="667d8-133">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="667d8-133">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="667d8-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="667d8-134">See also</span></span>

- [<span data-ttu-id="667d8-135">런타임에서 어셈블리를 찾는 방법</span><span class="sxs-lookup"><span data-stu-id="667d8-135">How the Runtime Locates Assemblies</span></span>](../../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)
- [<span data-ttu-id="667d8-136">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="667d8-136">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
