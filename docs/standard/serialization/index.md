---
title: serialization - .NET
description: 이 문서에서는 이진 serialization, XML 및 SOAP serialization, JSON serialization을 비롯한 .NET serialization 기술에 관한 정보를 제공합니다.
ms.date: 09/02/2019
helpviewer_keywords:
- JSON serialization
- XML serialization, defined
- binary serialization
- serializing objects
- serialization
- objects, serializing
ms.assetid: 4d1111c0-9447-4231-a997-96a2b74b3453
ms.openlocfilehash: b3d76c14dc9180a5f19781122d1a42bcae603e76
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "85840302"
---
# <a name="serialization-in-net"></a><span data-ttu-id="4eca0-103">.NET의 Serialization</span><span class="sxs-lookup"><span data-stu-id="4eca0-103">Serialization in .NET</span></span>

<span data-ttu-id="4eca0-104">serialization은 지속시키거나 전송할 수 있는 형태로 개체 상태를 변환하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-104">Serialization is the process of converting the state of an object into a form that can be persisted or transported.</span></span> <span data-ttu-id="4eca0-105">serialization과 짝을 이루는 것은 스트림을 개체로 변환하는 deserialization입니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-105">The complement of serialization is deserialization, which converts a stream into an object.</span></span> <span data-ttu-id="4eca0-106">이 프로세스를 함께 사용하여 데이터를 쉽게 저장하고 전송할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-106">Together, these processes allow data to be stored and transferred.</span></span>  
  
<span data-ttu-id="4eca0-107">.NET은 다음과 같은 serialization 기술을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-107">.NET features the following serialization technologies:</span></span>  
  
- <span data-ttu-id="4eca0-108">[이진 serialization](binary-serialization.md)은 형식 정확도를 유지하므로 애플리케이션의 여러 호출 간에 개체 상태를 유지하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-108">[Binary serialization](binary-serialization.md) preserves type fidelity, which is useful for preserving the state of an object between different invocations of an application.</span></span> <span data-ttu-id="4eca0-109">예를 들어, 개체를 클립보드로 serialize하면 여러 애플리케이션 간에 개체를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-109">For example, you can share an object between different applications by serializing it to the Clipboard.</span></span> <span data-ttu-id="4eca0-110">개체를 스트림, 디스크, 메모리, 네트워크 등으로 serialize할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-110">You can serialize an object to a stream, to a disk, to memory, over the network, and so forth.</span></span> <span data-ttu-id="4eca0-111">Remoting에서는 serialization을 사용하여 한 컴퓨터 또는 애플리케이션 도메인의 개체를 다른 컴퓨터 또는 애플리케이션 도메인으로 &quot;값으로&quot; 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-111">Remoting uses serialization to pass objects "by value" from one computer or application domain to another.</span></span>  
  
- <span data-ttu-id="4eca0-112">[XML 및 SOAP serialization](xml-and-soap-serialization.md)은 public 속성과 필드만 직렬화하며 형식 정확도를 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-112">[XML and SOAP serialization](xml-and-soap-serialization.md) serializes only public properties and fields and does not preserve type fidelity.</span></span> <span data-ttu-id="4eca0-113">데이터를 사용하는 애플리케이션을 제한하지 않고 데이터를 제공하거나 사용하려고 할 때 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-113">This is useful when you want to provide or consume data without restricting the application that uses the data.</span></span> <span data-ttu-id="4eca0-114">XML은 공개 표준이기 때문에 웹을 통해 정보를 공유할 때 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-114">Because XML is an open standard, it is an attractive choice for sharing data across the Web.</span></span> <span data-ttu-id="4eca0-115">SOAP도 마찬가지로 공개 표준이어서 적합한 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-115">SOAP is likewise an open standard, which makes it an attractive choice.</span></span>  
  
- <span data-ttu-id="4eca0-116">[JSON serialization](system-text-json-overview.md)은 public 속성만 직렬화하며 형식 정확도를 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-116">[JSON serialization](system-text-json-overview.md) serializes only public properties and does not preserve type fidelity.</span></span> <span data-ttu-id="4eca0-117">JSON은 웹을 통해 데이터를 공유할 때 적합한 공개 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-117">JSON is an open standard that is an attractive choice for sharing data across the web.</span></span>

## <a name="reference"></a><span data-ttu-id="4eca0-118">참고</span><span class="sxs-lookup"><span data-stu-id="4eca0-118">Reference</span></span>

<xref:System.Runtime.Serialization>  
<span data-ttu-id="4eca0-119">개체를 직렬화하거나 역직렬화하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-119">Contains classes that can be used for serializing and deserializing objects.</span></span>
  
<xref:System.Xml.Serialization>  
<span data-ttu-id="4eca0-120">개체를 XML 형식 문서 또는 스트림으로 serialize하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-120">Contains classes that can be used to serialize objects into XML format documents or streams.</span></span>

<xref:System.Text.Json>  
<span data-ttu-id="4eca0-121">개체를 JSON 형식 문서 또는 스트림으로 직렬화하는 데 사용할 수 있는 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4eca0-121">Contains classes that can be used to serialize objects into JSON format documents or streams.</span></span>
