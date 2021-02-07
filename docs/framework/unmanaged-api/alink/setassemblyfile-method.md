---
description: '자세히 알아보기: SetAssemblyFile 메서드'
title: SetAssemblyFile 메서드
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 943e0600b9781aeaf45cc26e39bd8a8b33a783c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662496"
---
# <a name="setassemblyfile-method"></a><span data-ttu-id="e48d1-103">SetAssemblyFile 메서드</span><span class="sxs-lookup"><span data-stu-id="e48d1-103">SetAssemblyFile Method</span></span>

<span data-ttu-id="e48d1-104">빌드할 어셈블리의 이름을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-104">Assigns the name of the assembly to be built.</span></span> <span data-ttu-id="e48d1-105">바인딩되지 않은 모듈을 생성할 때 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-105">Not for use when producing unbound modules.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e48d1-106">구문</span><span class="sxs-lookup"><span data-stu-id="e48d1-106">Syntax</span></span>  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e48d1-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e48d1-107">Parameters</span></span>  

 `pszFilename`  
 <span data-ttu-id="e48d1-108">매니페스트 파일의 정규화 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-108">Fully qualified name of the manifest file.</span></span>  
  
 `pEmitter`  
 <span data-ttu-id="e48d1-109">[IMetaDataEmit interface](../metadata/imetadataemit-interface.md) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-109">Pointer to [IMetaDataEmit Interface](../metadata/imetadataemit-interface.md) interface.</span></span>  
  
 `afFlags`  
 <span data-ttu-id="e48d1-110">[Assemblyflags 열거형](../metadata/assemblyflags-enumeration.md)에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-110">Flags as defined in [AssemblyFlags Enumeration](../metadata/assemblyflags-enumeration.md).</span></span>  
  
 `pAssemblyID`  
 <span data-ttu-id="e48d1-111">결과 어셈블리의 ID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-111">Pointer to ID of resulting assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e48d1-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="e48d1-112">Return Value</span></span>  

 <span data-ttu-id="e48d1-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e48d1-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e48d1-114">Requirements</span></span>  

 <span data-ttu-id="e48d1-115">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e48d1-115">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e48d1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e48d1-116">See also</span></span>

- [<span data-ttu-id="e48d1-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e48d1-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e48d1-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e48d1-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e48d1-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="e48d1-119">ALink API</span></span>](index.md)
