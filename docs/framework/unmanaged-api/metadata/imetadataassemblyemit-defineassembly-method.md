---
title: IMetaDataAssemblyEmit::DefineAssembly 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.DefineAssembly
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::DefineAssembly
helpviewer_keywords:
- IMetaDataAssemblyEmit::DefineAssembly method [.NET Framework metadata]
- DefineAssembly method [.NET Framework metadata]
ms.assetid: a0637d66-74bf-4f2d-8137-9ff838bccece
topic_type:
- apiref
ms.openlocfilehash: 14bd352099890e4ca36321d550b8e982d4373231
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177897"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="d05f4-102">IMetaDataAssemblyEmit::DefineAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="d05f4-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="d05f4-103">지정된 `Assembly` 어셈블리에 대한 메타데이터가 포함된 구조를 만들고 연결된 메타데이터 토큰을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d05f4-104">구문</span><span class="sxs-lookup"><span data-stu-id="d05f4-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineAssembly (  
    [in]  void                 *pbPublicKey,  
    [in]  ULONG                cbPublicKey,  
    [in]  ULONG                uHashAlgId,  
    [in]  LPCWSTR              szName,
    [in]  ASSEMBLYMETADATA     *pMetaData,  
    [in]  DWORD                dwAssemblyFlags,  
    [out] mdAssembly           *pmda  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d05f4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d05f4-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="d05f4-106">【인】 어셈블리의 게시자를 식별하는 공개 키 또는 어셈블리의 이름이 지정되지 않은 경우 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="d05f4-107">【인】 의 바이트 크기입니다. `pbPublicKey`</span><span class="sxs-lookup"><span data-stu-id="d05f4-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="d05f4-108">【인】 어셈블리의 파일을 암호화하는 데 사용할 해싱 알고리즘또는 NULL을 사용하여 SHA-1 알고리즘을 지정하는 데 사용할 해시 알고리즘의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="d05f4-109">【인】 어셈블리의 사람이 읽을 수 있는 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="d05f4-110">이 값은 1024자를 초과해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="d05f4-111">【인】 어셈블리에 대한 버전, 플랫폼 및 로캘 정보를 포함하는 ASSEMBLYMETADATA 인스턴스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="d05f4-112">【인】 [어셈블리의](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 기능을 설명하는 CorAssemblyFlags 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="d05f4-113">【아웃】 메타데이터 토큰에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d05f4-114">설명</span><span class="sxs-lookup"><span data-stu-id="d05f4-114">Remarks</span></span>  
 <span data-ttu-id="d05f4-115">매니페스트 `Assembly` 내에서 하나의 메타데이터 구조만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d05f4-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d05f4-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d05f4-116">Requirements</span></span>  
 <span data-ttu-id="d05f4-117">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d05f4-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d05f4-118">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="d05f4-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d05f4-119">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="d05f4-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d05f4-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d05f4-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d05f4-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d05f4-121">See also</span></span>

- [<span data-ttu-id="d05f4-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d05f4-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
