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
ms.openlocfilehash: 53ca4005f5681cfc5d550301d8aad1406aceb3a2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717203"
---
# <a name="addfile-method"></a><span data-ttu-id="62a3f-102">AddFile 메서드</span><span class="sxs-lookup"><span data-stu-id="62a3f-102">AddFile Method</span></span>

<span data-ttu-id="62a3f-103">어셈블리에 파일을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-103">Adds files to the assembly.</span></span> <span data-ttu-id="62a3f-104">바인딩되지 않은 모듈을 만드는 데 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-104">Can also be used to create unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="62a3f-105">구문</span><span class="sxs-lookup"><span data-stu-id="62a3f-105">Syntax</span></span>  
  
```cpp  
HRESULT AddFile(  
    mdAssembly      AssemblyID,  
    LPCWSTR         pszFilename,  
    DWORD           dwFlags,  
    IMetaDataEmit*  pEmitter,  
    mdFile*         pFileToken  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="62a3f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="62a3f-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="62a3f-107">확대할 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-107">Unique ID of the assembly to be augmented.</span></span>  
  
 `pszFilename`  
 <span data-ttu-id="62a3f-108">추가할 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-108">Fully qualified name of file to be added.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="62a3f-109">및와 같은 COM + FileDef 플래그 `ffContainsNoMetaData` `ffWriteable` 입니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-109">COM+ FileDef flags such as `ffContainsNoMetaData` and `ffWriteable`.</span></span> <span data-ttu-id="62a3f-110">`dwFlags`[DefineFile 메서드에](../metadata/imetadataassemblyemit-definefile-method.md)전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-110">`dwFlags` is passed to [DefineFile Method](../metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="62a3f-111">필요한 경우 메타 데이터를 내보내는 데 사용할 [IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-111">[IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface to be used to emit metadata, if necessary.</span></span>  
  
 `pFileToken`  
 <span data-ttu-id="62a3f-112">추가 된 파일의 고유 ID가 저장 될 위치에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-112">Pointer to where the unique ID of the added file will be stored.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="62a3f-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="62a3f-113">Return Value</span></span>  

 <span data-ttu-id="62a3f-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="62a3f-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="62a3f-115">Requirements</span></span>  

 <span data-ttu-id="62a3f-116">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="62a3f-116">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="62a3f-117">참조</span><span class="sxs-lookup"><span data-stu-id="62a3f-117">See also</span></span>

- [<span data-ttu-id="62a3f-118">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62a3f-118">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="62a3f-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="62a3f-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="62a3f-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="62a3f-120">ALink API</span></span>](index.md)
