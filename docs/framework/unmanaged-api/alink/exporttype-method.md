---
description: '자세한 정보: ExportType 메서드'
title: ExportType 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportType
helpviewer_keywords:
- ExportType method
ms.assetid: 91a7ce63-f5b8-4f16-b2c4-e1d0baa88944
topic_type:
- apiref
ms.openlocfilehash: 6dc047cac3b80e6fe7a6f2cd980061b34bb7f286
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638069"
---
# <a name="exporttype-method"></a><span data-ttu-id="09e90-103">ExportType 메서드</span><span class="sxs-lookup"><span data-stu-id="09e90-103">ExportType Method</span></span>

<span data-ttu-id="09e90-104">형식을 내보낼 수 있도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-104">Specifies that a type is exportable.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09e90-105">구문</span><span class="sxs-lookup"><span data-stu-id="09e90-105">Syntax</span></span>  
  
```cpp  
HRESULT ExportType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="09e90-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09e90-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="09e90-107">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-107">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="09e90-108">내보낼 수 있는 형식을 정의 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-108">File token or assembly ID of file that defines the exportable type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="09e90-109">내보낼 수 있도록 설정할 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-109">Token of type to be made exportable.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="09e90-110">내보낼 수 있는 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-110">Fully qualified type name to be made exportable.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="09e90-111">`ComType` 또는와 같은 `tdPublic` 플래그 `tdNested` 입니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span> <span data-ttu-id="09e90-112">이 매개 변수는 [DefineExportedType 메서드에](../metadata/imetadataassemblyemit-defineexportedtype-method.md)전달 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-112">This parameter may be passed to [DefineExportedType Method](../metadata/imetadataassemblyemit-defineexportedtype-method.md).</span></span>  
  
 `pType`  
 <span data-ttu-id="09e90-113">내보낸 형식에 대 한 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-113">Receives token for exported type.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="09e90-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="09e90-114">Return Value</span></span>  

 <span data-ttu-id="09e90-115">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="09e90-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09e90-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09e90-116">Requirements</span></span>  

 <span data-ttu-id="09e90-117">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="09e90-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09e90-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="09e90-118">See also</span></span>

- [<span data-ttu-id="09e90-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09e90-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="09e90-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09e90-120">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="09e90-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="09e90-121">ALink API</span></span>](index.md)
