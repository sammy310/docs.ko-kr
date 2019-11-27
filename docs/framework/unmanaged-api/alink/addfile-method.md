---
title: AddFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.AddFile
- AddFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AddFile
helpviewer_keywords:
- AddFile method
ms.assetid: 9e707abb-f905-4568-9356-12aa21d1b11c
topic_type:
- apiref
ms.openlocfilehash: 4dd104805d547613315335bc9c95b5c60a9cab14
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446677"
---
# <a name="addfile-method"></a><span data-ttu-id="0316c-102">AddFile 메서드</span><span class="sxs-lookup"><span data-stu-id="0316c-102">AddFile Method</span></span>
<span data-ttu-id="0316c-103">어셈블리에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-103">Adds files to the assembly.</span></span> <span data-ttu-id="0316c-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0316c-105">구문</span><span class="sxs-lookup"><span data-stu-id="0316c-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="0316c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0316c-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0316c-107">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="0316c-108">추가할 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="0316c-109">`ffContainsNoMetaData` 및 `ffWriteable`와 같은 COM + FileDef 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="0316c-110">`dwFlags` [DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="0316c-111">필요한 경우 메타 데이터를 내보내는 데 사용할 [IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="0316c-112">추가 된 파일의 고유 ID가 저장 될 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0316c-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="0316c-113">Return Value</span></span>  
 <span data-ttu-id="0316c-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0316c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0316c-115">Requirements</span></span>  
 <span data-ttu-id="0316c-116">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0316c-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0316c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0316c-117">See also</span></span>

- [<span data-ttu-id="0316c-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0316c-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0316c-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0316c-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0316c-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="0316c-120">ALink API</span></span>](index.md)
