---
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
ms.openlocfilehash: 7c6adcbcfe64f63048078b4ccba6727a58531033
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008107"
---
# <a name="imetadataassemblyemitsetassemblyprops-method"></a><span data-ttu-id="8bbcf-102">IMetaDataAssemblyEmit::SetAssemblyProps 메서드</span><span class="sxs-lookup"><span data-stu-id="8bbcf-102">IMetaDataAssemblyEmit::SetAssemblyProps Method</span></span>
<span data-ttu-id="8bbcf-103">지정된 `Assembly` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-103">Modifies the specified `Assembly` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bbcf-104">구문</span><span class="sxs-lookup"><span data-stu-id="8bbcf-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8bbcf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8bbcf-105">Parameters</span></span>  
 `pma`  
 <span data-ttu-id="8bbcf-106">진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `Assembly` .</span><span class="sxs-lookup"><span data-stu-id="8bbcf-106">[in] The metadata token that specifies the `Assembly` metadata structure to be modified.</span></span>  
  
 `pbPublicKey`  
 <span data-ttu-id="8bbcf-107">진행 어셈블리 게시자의 공개 키에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-107">[in] A pointer to the public key of the publisher of the assembly.</span></span>  
  
 `cbPublicKey`  
 <span data-ttu-id="8bbcf-108">진행 의 크기 (바이트) `pbPublicKey` 입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-108">[in] The size in bytes of `pbPublicKey`.</span></span>  
  
 `ulHashAlgId`  
 <span data-ttu-id="8bbcf-109">진행 어셈블리 파일을 해시 하는 데 사용 되는 해시 알고리즘의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-109">[in] The identifier for the hash algorithm used to hash the assembly files.</span></span>  
  
 `szName`  
 <span data-ttu-id="8bbcf-110">진행 사람이 읽을 수 있는 어셈블리의 텍스트 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-110">[in] The human-readable text name of the assembly.</span></span>  
  
 `pMetaData`  
 <span data-ttu-id="8bbcf-111">진행 어셈블리에 대 한 버전, 플랫폼 및 로캘 정보를 포함 하는 ASSEMBLYMETADATA에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-111">[in] A pointer to the ASSEMBLYMETADATA that contains version, platform, and locale information for the assembly.</span></span>  
  
 `dwAssemblyFlags`  
 <span data-ttu-id="8bbcf-112">진행 어셈블리의 다양 한 특성을 지정 하는 [Assemblyflags](assemblyflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-112">[in] A bitwise combination of [AssemblyFlags](assemblyflags-enumeration.md) values that specify various attributes of the assembly.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8bbcf-113">설명</span><span class="sxs-lookup"><span data-stu-id="8bbcf-113">Remarks</span></span>  
 <span data-ttu-id="8bbcf-114">`Assembly`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineAssembly](imetadataassemblyemit-defineassembly-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-114">To create an `Assembly` metadata structure, use the [IMetaDataAssemblyEmit::DefineAssembly](imetadataassemblyemit-defineassembly-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bbcf-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8bbcf-115">Requirements</span></span>  
 <span data-ttu-id="8bbcf-116">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-116">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bbcf-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8bbcf-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bbcf-118">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8bbcf-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bbcf-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bbcf-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbcf-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8bbcf-120">See also</span></span>

- [<span data-ttu-id="8bbcf-121">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8bbcf-121">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
