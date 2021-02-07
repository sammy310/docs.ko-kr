---
description: '자세히 알아보기: IMetaDataAssemblyEmit:: SetAssemblyProps 메서드'
title: IMetaDataAssemblyEmit::SetAssemblyProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetAssemblyProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetAssemblyProps
helpviewer_keywords:
- SetAssemblyProps method [.NET Framework metadata]
- IMetaDataAssemblyEmit::SetAssemblyProps method [.NET Framework metadata]
ms.assetid: 91b633d7-9e75-43c3-a8d2-2144984e5f9e
topic_type:
- apiref
ms.openlocfilehash: d5dfb5fa472bb83863c8e4909998deeb2b9fc53b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678200"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="31d36-103">IMetaDataAssemblyEmit::SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="31d36-103">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>

<span data-ttu-id="31d36-104">지정된 `Assembly` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-104">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="31d36-105">구문</span><span class="sxs-lookup"><span data-stu-id="31d36-105">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyProps (  
    [in] mdAssembly               pma,  
    [in] const void               *pbPublicKey,  
    [in] ULONG                    cbPublicKey,  
    [in] ULONG                    ulHashAlgId,  
    [in] LPCWSTR                  szName,  
    [in] const ASSEMBLYMETADATA   *pMetaData,  
    [in] DWORD                    dwAssemblyFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="31d36-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="31d36-106">Parameters</span></span>  

 `pma`  
 <span data-ttu-id="31d36-107">진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `Assembly` .</span><span class="sxs-lookup"><span data-stu-id="31d36-107">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="31d36-108">진행 어셈블리 게시자의 공개 키에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-108">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="31d36-109">진행 의 크기 (바이트) `pbPublicKey` 입니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-109">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="31d36-110">진행 어셈블리 파일을 해시 하는 데 사용 되는 해시 알고리즘의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-110">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="31d36-111">진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-111">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="31d36-112">진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-112">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="31d36-113">진행 어셈블리의 다양 한 특성을 지정 하는 [Assemblyflags](assemblyflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-113">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="31d36-114">설명</span><span class="sxs-lookup"><span data-stu-id="31d36-114">Remarks</span></span>  

 <span data-ttu-id="31d36-115">`Assembly`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineAssembly](imetadataassemblyemit-defineassembly-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-115">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="31d36-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="31d36-116">Requirements</span></span>  

 <span data-ttu-id="31d36-117">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="31d36-117">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31d36-118">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="31d36-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="31d36-119">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="31d36-119">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="31d36-120">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="31d36-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31d36-121">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31d36-121">See also</span></span>

- [<span data-ttu-id="31d36-122">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="31d36-122">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
