---
title: ExportNestedType 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
ms.openlocfilehash: 69c99e2facfcb9077c3fc4131186ba3882c7cef6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684839"
---
# <a name="exportnestedtype-method"></a><span data-ttu-id="27a52-102">ExportNestedType 메서드</span><span class="sxs-lookup"><span data-stu-id="27a52-102">ExportNestedType Method</span></span>

<span data-ttu-id="27a52-103">중첩 형식을 내보낼 수 있는 형식으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-103">Specifies nested types as exportable.</span></span> <span data-ttu-id="27a52-104">[Exporttype 메서드](exporttype-method.md) 는 중첩 형식을 내보낼 수도 있지만이 메서드는 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-104">The [ExportType Method](exporttype-method.md) can also export nested types, but this method is faster.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27a52-105">구문</span><span class="sxs-lookup"><span data-stu-id="27a52-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="27a52-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27a52-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="27a52-107">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-107">ID of assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="27a52-108">내보낼 수 있는 형식을 정의 하는 파일의 파일 토큰 또는 어셈블리입니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-108">File token or Assembly of file that defines the type to be made exportable.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="27a52-109">내보낼 수 있는 형식의 형식 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-109">Type token of type to be made exportable.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="27a52-110">부모 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="27a52-111">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="27a52-112">`ComType` 또는와 같은 `tdPublic` 플래그 `tdNested` 입니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="27a52-113">이 값은 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-113">This value may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="27a52-114">내보낸 형식에 대 한 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-114">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="27a52-115">반환 값</span><span class="sxs-lookup"><span data-stu-id="27a52-115">Return Value</span></span>  

 <span data-ttu-id="27a52-116">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="27a52-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27a52-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27a52-117">Requirements</span></span>  

 <span data-ttu-id="27a52-118">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="27a52-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27a52-119">참조</span><span class="sxs-lookup"><span data-stu-id="27a52-119">See also</span></span>

- [<span data-ttu-id="27a52-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27a52-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="27a52-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27a52-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="27a52-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="27a52-122">ALink API</span></span>](index.md)
