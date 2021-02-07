---
description: '자세히 알아보기: IMetaDataAssemblyImport:: EnumFiles 메서드'
title: IMetaDataAssemblyImport::EnumFiles 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.EnumFiles
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::EnumFiles
helpviewer_keywords:
- IMetaDataAssemblyImport::EnumFiles method [.NET Framework metadata]
- EnumFiles method [.NET Framework metadata]
ms.assetid: f0d721e2-b946-426d-8e20-9124bd04e4cb
topic_type:
- apiref
ms.openlocfilehash: 25282edd081e937e4c84334f9f004e201b9db46f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99671024"
---
# <a name="imetadataassemblyimportenumfiles-method"></a><span data-ttu-id="b899f-103">IMetaDataAssemblyImport::EnumFiles 메서드</span><span class="sxs-lookup"><span data-stu-id="b899f-103">IMetaDataAssemblyImport::EnumFiles Method</span></span>

<span data-ttu-id="b899f-104">현재 어셈블리 매니페스트에서 참조 하는 파일을 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-104">Enumerates the files referenced in the current assembly manifest.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b899f-105">구문</span><span class="sxs-lookup"><span data-stu-id="b899f-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumFiles (  
    [in, out] HCORENUM    *phEnum,
    [out] mdFile          rFiles[],
    [in]  ULONG           cMax,
    [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b899f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b899f-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="b899f-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="b899f-108">이 메서드의 첫 번째 호출에는 null 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-108">This must be a null value for the first call of this method.</span></span>  
  
 `rFiles`  
 <span data-ttu-id="b899f-109">제한이 메타 데이터 토큰을 저장 하는 데 사용 되는 배열 `mdFile` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-109">[out] The array used to store the `mdFile` metadata tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="b899f-110">진행 `mdFile` 에 배치할 수 있는 최대 토큰 수입니다 `rFiles` .</span><span class="sxs-lookup"><span data-stu-id="b899f-110">[in] The maximum number of `mdFile` tokens that can be placed in `rFiles`.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="b899f-111">제한이 `mdFile` 에 실제로 배치 된 토큰의 수 `rFiles` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-111">[out] The number of `mdFile` tokens actually placed in `rFiles`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b899f-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="b899f-112">Return Value</span></span>  
  
|<span data-ttu-id="b899f-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b899f-113">HRESULT</span></span>|<span data-ttu-id="b899f-114">설명</span><span class="sxs-lookup"><span data-stu-id="b899f-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b899f-115">`EnumFiles` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-115">`EnumFiles` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="b899f-116">열거할 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="b899f-117">이 경우 `pcTokens` 는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-117">In this case, `pcTokens` is set to zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b899f-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b899f-118">Requirements</span></span>  

 <span data-ttu-id="b899f-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b899f-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b899f-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b899f-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b899f-121">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b899f-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b899f-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b899f-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b899f-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b899f-123">See also</span></span>

- [<span data-ttu-id="b899f-124">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b899f-124">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
