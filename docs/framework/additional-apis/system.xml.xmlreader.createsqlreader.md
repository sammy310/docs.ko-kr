---
title: XmlReader.CreateSqlReader 방법 (System.Xml)
ms.date: 10/17/2019
topic_type:
- apiref
api_name:
- System.Xml.XmlReader.CreateSqlReader
api_location:
- system.xml.dll
api_type:
- Assembly
ms.openlocfilehash: 7bd2ef5158516acede47f73f9937d06159bc16c9
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79155741"
---
# <a name="xmlreadercreatesqlreader-method"></a><span data-ttu-id="37a17-102">XmlReader.CreateSqlReader 메서드</span><span class="sxs-lookup"><span data-stu-id="37a17-102">XmlReader.CreateSqlReader Method</span></span>

<span data-ttu-id="37a17-103">구문 분석을 위해 지정한 스트림, 설정 및 컨텍스트 정보를 사용하여 새 <xref:System.Xml.XmlReader> 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-103">Creates a new <xref:System.Xml.XmlReader> instance using the specified stream, settings, and context information for parsing.</span></span>

```csharp
internal static XmlReader CreateSqlReader(Stream input,
  XmlReaderSettings settings, XmlParserContext inputContext)
```

## <a name="parameters"></a><span data-ttu-id="37a17-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="37a17-104">Parameters</span></span>

- <span data-ttu-id="37a17-105">`input` <xref:System.IO.Stream></span><span class="sxs-lookup"><span data-stu-id="37a17-105">`input` <xref:System.IO.Stream></span></span>  
  <span data-ttu-id="37a17-106">XML 데이터가 포함된 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-106">The stream that contains the XML data.</span></span>

- <span data-ttu-id="37a17-107">`settings` <xref:System.Xml.XmlReaderSettings></span><span class="sxs-lookup"><span data-stu-id="37a17-107">`settings` <xref:System.Xml.XmlReaderSettings></span></span>  
  <span data-ttu-id="37a17-108">새 <xref:System.Xml.XmlReader> 인스턴스의 설정입니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-108">The settings for the new <xref:System.Xml.XmlReader> instance.</span></span> <span data-ttu-id="37a17-109">이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-109">This value can be `null`.</span></span>

- <span data-ttu-id="37a17-110">`inputContext` <xref:System.Xml.XmlParserContext></span><span class="sxs-lookup"><span data-stu-id="37a17-110">`inputContext` <xref:System.Xml.XmlParserContext></span></span>  
  <span data-ttu-id="37a17-111">XML 조각을 구문 분석하는 데 필요한 컨텍스트 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-111">The context information required to parse the XML fragment.</span></span> <span data-ttu-id="37a17-112">이 값은 `null`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-112">This value can be `null`.</span></span>

## <a name="returns"></a><span data-ttu-id="37a17-113">반환</span><span class="sxs-lookup"><span data-stu-id="37a17-113">Returns</span></span>

<xref:System.Xml.XmlReader>  
<span data-ttu-id="37a17-114">스트림의 XML 데이터를 읽는 데 사용되는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-114">An object that is used to read the XML data in the stream.</span></span>

## <a name="remarks"></a><span data-ttu-id="37a17-115">설명</span><span class="sxs-lookup"><span data-stu-id="37a17-115">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="37a17-116">메서드는 `XmlReader.CreateSqlReader` 내부이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-116">The `XmlReader.CreateSqlReader` method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="37a17-117">Microsoft는 어떠한 상황에서도 프로덕션 응용 프로그램에서 이 메서드의 사용을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-117">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="37a17-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="37a17-118">Requirements</span></span>

<span data-ttu-id="37a17-119">**네임스페이스:**<xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="37a17-119">**Namespace:** <xref:System.Xml></span></span>

<span data-ttu-id="37a17-120">**어셈블리:** 시스템.Xml.dll</span><span class="sxs-lookup"><span data-stu-id="37a17-120">**Assembly:** System.Xml.dll</span></span>

<span data-ttu-id="37a17-121">**.NET 프레임워크 버전:** 2.0 부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="37a17-121">**.NET Framework versions:** Available since 2.0.</span></span>
