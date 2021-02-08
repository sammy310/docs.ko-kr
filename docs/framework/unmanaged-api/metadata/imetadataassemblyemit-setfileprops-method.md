---
description: '자세히 알아보기: IMetaDataAssemblyEmit:: SetFileProps 메서드'
title: IMetaDataAssemblyEmit::SetFileProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyEmit.SetFileProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyEmit::SetFileProps
helpviewer_keywords:
- IMetaDataAssemblyEmit::SetFileProps method [.NET Framework metadata]
- SetFileProps method [.NET Framework metadata]
ms.assetid: 85667d38-611c-45a9-938d-930ac7a7b681
topic_type:
- apiref
ms.openlocfilehash: 482aa11b85eaf05d126c4fcc0d5a1aced85002d4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789309"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="50328-103">IMetaDataAssemblyEmit::SetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="50328-103">IMetaDataAssemblyEmit::SetFileProps Method</span></span>

<span data-ttu-id="50328-104">지정된 `File` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="50328-104">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="50328-105">구문</span><span class="sxs-lookup"><span data-stu-id="50328-105">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="50328-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="50328-106">Parameters</span></span>  

 `file`  
 <span data-ttu-id="50328-107">진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `File` .</span><span class="sxs-lookup"><span data-stu-id="50328-107">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="50328-108">진행 파일과 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="50328-108">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="50328-109">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="50328-109">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="50328-110">진행 파일의 다양 한 특성을 지정 하는 [Corfileflags](corfileflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="50328-110">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="50328-111">설명</span><span class="sxs-lookup"><span data-stu-id="50328-111">Remarks</span></span>  

 <span data-ttu-id="50328-112">`File`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineFile](imetadataassemblyemit-definefile-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50328-112">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="50328-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="50328-113">Requirements</span></span>  

 <span data-ttu-id="50328-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="50328-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="50328-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="50328-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="50328-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50328-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="50328-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="50328-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="50328-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50328-118">See also</span></span>

- [<span data-ttu-id="50328-119">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="50328-119">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
