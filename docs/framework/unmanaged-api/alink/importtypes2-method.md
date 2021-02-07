---
description: '자세히 알아보기: ImportTypes2 메서드'
title: ImportTypes2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: ca0d174061608f9b4abf524c43023e867e9a9646
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662613"
---
# <a name="importtypes2-method"></a><span data-ttu-id="fe515-103">ImportTypes2 메서드</span><span class="sxs-lookup"><span data-stu-id="fe515-103">ImportTypes2 Method</span></span>

<span data-ttu-id="fe515-104">형식의 가져오기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-104">Initiates the import of types.</span></span> <span data-ttu-id="fe515-105">[Importfile 메서드](importfile-method.md)를 통해 가져온 각 범위에서 형식 가져오기를 시작 하려면이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-105">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe515-106">구문</span><span class="sxs-lookup"><span data-stu-id="fe515-106">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="fe515-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fe515-107">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="fe515-108">가져올 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-108">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="fe515-109">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-109">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="fe515-110">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-110">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="fe515-111">지정 된 범위에 있는 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-111">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="fe515-112">선택적으로 [IMetaDataImport2 인터페이스](../metadata/imetadataimport2-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-112">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="fe515-113">선택적으로 지정 된 범위에 있는 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-113">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="fe515-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="fe515-114">Return Value</span></span>  

 <span data-ttu-id="fe515-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fe515-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe515-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fe515-116">Requirements</span></span>  

 <span data-ttu-id="fe515-117">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="fe515-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe515-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fe515-118">See also</span></span>

- [<span data-ttu-id="fe515-119">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe515-119">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="fe515-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fe515-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="fe515-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="fe515-121">ALink API</span></span>](index.md)
