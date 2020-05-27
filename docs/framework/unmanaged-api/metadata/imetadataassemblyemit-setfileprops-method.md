---
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
ms.openlocfilehash: 9990daea1b097532de53684921d3f10c520a3b1a
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008068"
---
# <a name="imetadataassemblyemitsetfileprops-method"></a><span data-ttu-id="47f38-102">IMetaDataAssemblyEmit::SetFileProps 메서드</span><span class="sxs-lookup"><span data-stu-id="47f38-102">IMetaDataAssemblyEmit::SetFileProps Method</span></span>
<span data-ttu-id="47f38-103">지정된 `File` 메타데이터 구조를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="47f38-103">Modifies the specified `File` metadata structure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47f38-104">구문</span><span class="sxs-lookup"><span data-stu-id="47f38-104">Syntax</span></span>  
  
```cpp  
HRESULT SetFileProps (  
    [in] mdFile        file,  
    [in] const void    *pbHashValue,
    [in] ULONG         cbHashValue,  
    [in] DWORD         dwFileFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47f38-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="47f38-105">Parameters</span></span>  
 `file`  
 <span data-ttu-id="47f38-106">진행 수정할 메타 데이터 구조를 지정 하는 메타 데이터 토큰입니다 `File` .</span><span class="sxs-lookup"><span data-stu-id="47f38-106">[in] The metadata token that specifies the `File` metadata structure to be modified.</span></span>  
  
 `pbHashValue`  
 <span data-ttu-id="47f38-107">진행 파일과 연결 된 해시 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="47f38-107">[in] A pointer to the hash data associated with the file.</span></span>  
  
 `cbHashValue`  
 <span data-ttu-id="47f38-108">진행 의 크기 (바이트) `pbHashValue` 입니다.</span><span class="sxs-lookup"><span data-stu-id="47f38-108">[in] The size in bytes of `pbHashValue`.</span></span>  
  
 `dwFileFlags`  
 <span data-ttu-id="47f38-109">진행 파일의 다양 한 특성을 지정 하는 [Corfileflags](corfileflags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="47f38-109">[in] A bitwise combination of [CorFileFlags](corfileflags-enumeration.md) values that specify various attributes of the file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="47f38-110">설명</span><span class="sxs-lookup"><span data-stu-id="47f38-110">Remarks</span></span>  
 <span data-ttu-id="47f38-111">`File`메타 데이터 구조를 만들려면 [IMetaDataAssemblyEmit::D efineFile](imetadataassemblyemit-definefile-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="47f38-111">To create a `File` metadata structure, use the [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="47f38-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="47f38-112">Requirements</span></span>  
 <span data-ttu-id="47f38-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="47f38-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47f38-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="47f38-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="47f38-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="47f38-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="47f38-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47f38-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47f38-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47f38-117">See also</span></span>

- [<span data-ttu-id="47f38-118">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="47f38-118">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
