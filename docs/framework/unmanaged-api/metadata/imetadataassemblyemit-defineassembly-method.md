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
ms.openlocfilehash: 6d783e27c60db7381025f3b2382728e3996323ae
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725731"
---
# <a name="imetadataassemblyemitdefineassembly-method"></a><span data-ttu-id="38fc3-102">IMetaDataAssemblyEmit::DefineAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="38fc3-102">IMetaDataAssemblyEmit::DefineAssembly Method</span></span>

<span data-ttu-id="38fc3-103">지정 된 `Assembly` 어셈블리에 대 한 메타 데이터를 포함 하는 구조체를 만들고 연결 된 메타 데이터 토큰을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-103">Creates an `Assembly` structure containing metadata for the specified assembly and returns the associated metadata token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38fc3-104">구문</span><span class="sxs-lookup"><span data-stu-id="38fc3-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="38fc3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="38fc3-105">Parameters</span></span>  

 `pbPublicKey`  
 <span data-ttu-id="38fc3-106">진행 어셈블리의 게시자를 식별 하는 공개 키 이거나, 어셈블리에 강력한 이름이 지정 되지 않은 경우 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-106">[in] The public key that identifies the publisher of the assembly, or NULL if the assembly is not strongly named.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="38fc3-107">진행 의 크기 (바이트) `pbPublicKey` 입니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-107">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `uHashAlgId`  
 <span data-ttu-id="38fc3-108">진행 어셈블리의 파일을 암호화 하는 데 사용할 해시 알고리즘의 식별자 이거나, SHA-1 알고리즘을 지정 하려면 NULL입니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-108">[in] The identifier of the hashing algorithm to use to encrypt the files in the assembly, or NULL to specify the SHA-1 algorithm.</span></span>  
  
 `szName`  
 <span data-ttu-id="38fc3-109">진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-109">[in] The human-readable text name of the assembly.</span></span> <span data-ttu-id="38fc3-110">이 값은 1024 자를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-110">This value must not exceed 1024 characters.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="38fc3-111">진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-111">[in] A pointer to an ASSEMBLYMETADATA instance that contains the version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="38fc3-112">진행 어셈블리의 기능을 설명 하는 [Corassemblyflags](corassemblyflags-enumeration.md) 값의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-112">[in] A combination of [CorAssemblyFlags](corassemblyflags-enumeration.md) values that describe features of the assembly.</span></span>  
  
 `pmda`  
 <span data-ttu-id="38fc3-113">제한이 메타 데이터 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-113">[out] A pointer to the metadata token.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="38fc3-114">설명</span><span class="sxs-lookup"><span data-stu-id="38fc3-114">Remarks</span></span>  

 <span data-ttu-id="38fc3-115">`Assembly`매니페스트 내에서 메타 데이터 구조를 하나만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-115">Only one `Assembly` metadata structure can be defined within a manifest.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="38fc3-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38fc3-116">Requirements</span></span>  

 <span data-ttu-id="38fc3-117">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="38fc3-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38fc3-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="38fc3-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="38fc3-119">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="38fc3-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="38fc3-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38fc3-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38fc3-121">참조</span><span class="sxs-lookup"><span data-stu-id="38fc3-121">See also</span></span>

- [<span data-ttu-id="38fc3-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38fc3-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
