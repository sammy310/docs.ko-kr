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
ms.openlocfilehash: 20628e708261076c6e172ff30c366a0d69c2e0f2
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74432126"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="62929-102">IMetaDataAssemblyEmit::DefineAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="62929-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>
<span data-ttu-id="62929-103">지정 된 어셈블리에 대 한 메타 데이터를 포함 하는 `Assembly` 구조체를 만들고 연결 된 메타 데이터 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="62929-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62929-104">구문</span><span class="sxs-lookup"><span data-stu-id="62929-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="62929-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62929-105">Parameters</span></span>  
 `pbPublicKey`  
 <span data-ttu-id="62929-106">진행 어셈블리의 게시자를 식별 하는 공개 키 이거나, 어셈블리에 강력한 이름이 지정 되지 않은 경우 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="62929-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="62929-107">진행 `pbPublicKey`의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="62929-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="62929-108">진행 어셈블리의 파일을 암호화 하는 데 사용할 해시 알고리즘의 식별자 이거나, SHA-1 알고리즘을 지정 하려면 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="62929-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="62929-109">진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="62929-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="62929-110">이 값은 1024 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="62929-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="62929-111">진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62929-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="62929-112">진행 어셈블리의 기능을 설명 하는 [Corassemblyflags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="62929-112">[in] A combination of [CorAssemblyFlags](../../../../docs/framework/unmanaged-api/metadata/corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="62929-113">제한이 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62929-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="62929-114">주의</span><span class="sxs-lookup"><span data-stu-id="62929-114">Remarks</span></span>  
 <span data-ttu-id="62929-115">매니페스트 내에는 하나의 `Assembly` 메타 데이터 구조만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62929-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62929-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62929-116">Requirements</span></span>  
 <span data-ttu-id="62929-117">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="62929-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="62929-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="62929-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="62929-119">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62929-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="62929-120">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="62929-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62929-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="62929-121">See also</span></span>

- [<span data-ttu-id="62929-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62929-122">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
