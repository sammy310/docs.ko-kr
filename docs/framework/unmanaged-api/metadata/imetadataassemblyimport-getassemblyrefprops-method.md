---
title: IMetaDataAssemblyImport::GetAssemblyRefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.GetAssemblyRefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps
helpviewer_keywords:
- IMetaDataAssemblyImport::GetAssemblyRefProps method [.NET Framework metadata]
- GetAssemblyRefProps method [.NET Framework metadata]
ms.assetid: 5c6b7fb4-cbca-4479-b650-ab9a99732ea0
topic_type:
- apiref
ms.openlocfilehash: 9aef471c1155070af0e9bcca14975a65bc5dc763
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175969"
---
# <a name="imetadataassemblyimportgetassemblyrefprops-method"></a><span data-ttu-id="1d3fe-102">IMetaDataAssemblyImport::GetAssemblyRefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="1d3fe-102">IMetaDataAssemblyImport::GetAssemblyRefProps Method</span></span>
<span data-ttu-id="1d3fe-103">지정된 메타데이터 서명을 통해 어셈블리 참조에 대한 속성 집합을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-103">Gets the set of properties for the assembly reference with the specified metadata signature.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d3fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="1d3fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetAssemblyRefProps (  
    [in]  mdAssemblyRef        mdar,
    [out] const void          **ppbPublicKeyOrToken,
    [out] ULONG                *pcbPublicKeyOrToken,
    [out] LPWSTR               szName,
    [in]  ULONG                cchName,
    [out] ULONG                *pchName,
    [out] ASSEMBLYMETADATA     *pMetaData,
    [out] const void           **ppbHashValue,
    [out] ULONG                *pcbHashValue,
    [out] DWORD                *pdwAssemblyRefFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1d3fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1d3fe-105">Parameters</span></span>  
 `mdar`  
 <span data-ttu-id="1d3fe-106">【인】 속성을 `mdAssemblyRef` 가져오는 어셈블리 참조를 나타내는 메타데이터 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-106">[in] The `mdAssemblyRef` metadata token that represents the assembly reference for which to get the properties.</span></span>  
  
 `ppbPublicKeyOrToken`  
 <span data-ttu-id="1d3fe-107">【아웃】 공개 키 또는 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-107">[out] A pointer to the public key or the metadata token.</span></span>  
  
 `pcbPublicKeyOrToken`  
 <span data-ttu-id="1d3fe-108">【아웃】 반환된 공개 키 또는 토큰의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-108">[out] The number of bytes in the returned public key or token.</span></span>  
  
 `szName`  
 <span data-ttu-id="1d3fe-109">【아웃】 어셈블리의 간단한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-109">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="1d3fe-110">【인】 크기, 와이드 문자, 의 `szName`.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-110">[in] The size, in wide chars, of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="1d3fe-111">【아웃】 실제로 반환된 와이드 문자 수에 `szName`대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-111">[out] A pointer to the number of wide chars actually returned in `szName`.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="1d3fe-112">【아웃】 어셈블리 메타데이터가 포함된 ASSEMBLYMETADATA 구조에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-112">[out] A pointer to an ASSEMBLYMETADATA structure that contains the assembly metadata.</span></span>  
  
 `ppbHashValue`  
 <span data-ttu-id="1d3fe-113">【아웃】 해시 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-113">[out] A pointer to the hash value.</span></span> <span data-ttu-id="1d3fe-114">이 해시는 `PublicKey` [어셈블리RefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) 열거형의 arfFullOriginator 플래그가 설정되지 않는 한 참조되는 어셈블리의 속성의 SHA-1 알고리즘을 사용하는 해시입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-114">This is the hash, using the SHA-1 algorithm, of the `PublicKey` property of the assembly being referenced, unless the arfFullOriginator flag of the [AssemblyRefFlags](../../../../docs/framework/unmanaged-api/metadata/assemblyrefflags-enumeration.md) enumeration is set.</span></span>  
  
 `pcbHashValue`  
 <span data-ttu-id="1d3fe-115">【아웃】 반환된 해시 값의 와이드 문자 수입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-115">[out] The number of wide chars in the returned hash value.</span></span>  
  
 `pdwAssemblyRefFlags`  
 <span data-ttu-id="1d3fe-116">【아웃】 어셈블리에 적용된 메타데이터를 설명하는 플래그에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-116">[out] A pointer to flags that describe the metadata applied to an assembly.</span></span> <span data-ttu-id="1d3fe-117">플래그 값은 하나 이상의 [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 플래그 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-117">The flags value is a combination of one or more [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1d3fe-118">Return Value</span><span class="sxs-lookup"><span data-stu-id="1d3fe-118">Return Value</span></span>  
 <span data-ttu-id="1d3fe-119">이 메서드는 성공하는 경우 S_OK 반환합니다. 그렇지 않으면 Winerror.h 헤더 파일에 정의된 오류 코드 중 하나를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-119">This method returns S_OK if it succeeds; otherwise, it returns one of the error codes defined in the Winerror.h header file.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1d3fe-120">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1d3fe-120">Requirements</span></span>  
 <span data-ttu-id="1d3fe-121">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d3fe-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d3fe-122">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="1d3fe-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d3fe-123">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="1d3fe-123">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d3fe-124">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d3fe-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d3fe-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d3fe-125">See also</span></span>

- [<span data-ttu-id="1d3fe-126">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1d3fe-126">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
