---
title: IMetaDataDispenser::OpenScopeOnMemory 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScopeOnMemory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScopeOnMemory
helpviewer_keywords:
- OpenScopeOnMemory method [.NET Framework metadata]
- IMetaDataDispenser::OpenScopeOnMemory method [.NET Framework metadata]
ms.assetid: 14218249-bdec-48ae-b5fc-9f57f7ca8501
topic_type:
- apiref
ms.openlocfilehash: 69e5e05012d2b44a76a986591ec990f66bf8ae20
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007327"
---
# <a name="imetadatadispenseropenscopeonmemory-method"></a><span data-ttu-id="d451d-102">IMetaDataDispenser::OpenScopeOnMemory 메서드</span><span class="sxs-lookup"><span data-stu-id="d451d-102">IMetaDataDispenser::OpenScopeOnMemory Method</span></span>
<span data-ttu-id="d451d-103">기존 메타 데이터를 포함 하는 메모리 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-103">Opens an area of memory that contains existing metadata.</span></span> <span data-ttu-id="d451d-104">즉,이 메서드는 기존 데이터가 메타 데이터로 처리 되는 지정 된 메모리 영역을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-104">That is, this method opens a specified area of memory in which the existing data is treated as metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d451d-105">구문</span><span class="sxs-lookup"><span data-stu-id="d451d-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnMemory (  
    [in]  LPCVOID     pData,
    [in]  ULONG       cbData,
    [in]  DWORD       dwOpenFlags,
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d451d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d451d-106">Parameters</span></span>  
 `pData`  
 <span data-ttu-id="d451d-107">진행 메모리 영역의 시작 주소를 지정 하는 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-107">[in] A pointer that specifies the starting address of the memory area.</span></span>  
  
 `cbData`  
 <span data-ttu-id="d451d-108">진행 메모리 영역의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-108">[in] The size of the memory area, in bytes.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="d451d-109">진행 열기에 대 한 모드 (읽기, 쓰기 등)를 지정 하는 [Coropenflags](coropenflags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-109">[in] A value of the [CorOpenFlags](coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="d451d-110">진행 반환할 원하는 메타 데이터 인터페이스의 IID입니다. 호출자는 인터페이스를 사용 하 여 메타 데이터를 가져오거나 (읽기) 내보내기 (쓰기) 합니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="d451d-111">값은 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-111">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="d451d-112">유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 또는 IID_IMetaDataImport2입니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="d451d-113">제한이 반환 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d451d-114">설명</span><span class="sxs-lookup"><span data-stu-id="d451d-114">Remarks</span></span>  
 <span data-ttu-id="d451d-115">메타 데이터의 메모리 내 복사본은 "가져오기" 인터페이스 중 하나에서 메서드를 사용 하 여 쿼리하거나 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-115">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="d451d-116">`OpenScopeOnMemory`이 메서드는 [IMetaDataDispenser:: openscope](imetadatadispenser-openscope-method.md) 메서드와 유사 합니다. 단, 대상 메타 데이터는 디스크의 파일이 아니라 메모리에 이미 존재 합니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-116">The `OpenScopeOnMemory` method is similar to the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, except that the metadata of interest already exists in memory, rather than in a file on disk.</span></span>  
  
 <span data-ttu-id="d451d-117">메모리의 대상 영역에 CLR (공용 언어 런타임) 메타 데이터가 포함 되어 있지 않으면 `OpenScopeOnMemory` 메서드는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-117">If the target area of memory does not contain common language runtime (CLR) metadata, the `OpenScopeOnMemory` method will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d451d-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d451d-118">Requirements</span></span>  
 <span data-ttu-id="d451d-119">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d451d-119">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d451d-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="d451d-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d451d-121">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d451d-121">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d451d-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d451d-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d451d-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d451d-123">See also</span></span>

- [<span data-ttu-id="d451d-124">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-124">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="d451d-125">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-125">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="d451d-126">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-126">IMetaDataAssemblyEmit Interface</span></span>](imetadataassemblyemit-interface.md)
- [<span data-ttu-id="d451d-127">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-127">IMetaDataAssemblyImport Interface</span></span>](imetadataassemblyimport-interface.md)
- [<span data-ttu-id="d451d-128">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="d451d-129">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="d451d-130">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-130">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="d451d-131">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d451d-131">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
