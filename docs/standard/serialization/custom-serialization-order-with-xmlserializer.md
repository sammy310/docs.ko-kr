---
title: XmlSerializer를 통한 사용자 지정 Serialization 순서
ms.date: 03/30/2017
ms.assetid: 975abd20-2a1d-42db-aed3-e898025ccce7
ms.openlocfilehash: c5934fd0cab03f754784c8515094ff4ec5e78ba4
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490927"
---
# <a name="custom-serialization-order-with-xmlserializer"></a><span data-ttu-id="3a160-102">XmlSerializer를 통한 사용자 지정 Serialization 순서</span><span class="sxs-lookup"><span data-stu-id="3a160-102">Custom Serialization Order With XmlSerializer</span></span>
[<span data-ttu-id="3a160-103">샘플 다운로드</span><span class="sxs-lookup"><span data-stu-id="3a160-103">Download Sample</span></span>](https://download.microsoft.com/download/4/7/B/47B2164C-E780-4B10-8DE4-2CB5B886E0A6/Technologies/Serialization/Xml%20Serialization/CustomOrder.zip.exe)  
  
 <span data-ttu-id="3a160-104">이 샘플에서는 XML serialization에서 직렬화 및 역직렬화되는 요소의 순서를 제어하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3a160-104">This sample shows how to control the order of serialized and deserialized elements for XML serialization.</span></span>  
  
 <span data-ttu-id="3a160-105">serialization에 대한 자세한 내용은 build.proj 파일 및 소스 코드의 주석을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="3a160-105">Review comments in the source code and build.proj files for more information on serialization.</span></span>  
  
### <a name="to-build-the-sample-using-the-command-prompt"></a><span data-ttu-id="3a160-106">명령 프롬프트를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="3a160-106">To build the sample using the Command Prompt</span></span>  
  
1. <span data-ttu-id="3a160-107">명령 프롬프트 창을 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a160-107">Open the Command Prompt window and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="3a160-108">명령줄에 **msbuild CustomOrder.sln**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="3a160-108">Type **msbuild CustomOrder.sln** at the command line.</span></span>  
  
### <a name="to-build-the-sample-using-visual-studio"></a><span data-ttu-id="3a160-109">Visual Studio를 사용하여 샘플을 빌드하려면</span><span class="sxs-lookup"><span data-stu-id="3a160-109">To build the sample using Visual Studio</span></span>  
  
1. <span data-ttu-id="3a160-110">파일 탐색기를 열고 샘플에 대한 언어별 하위 디렉터리 중 하나로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="3a160-110">Open File Explorer and navigate to one of the language-specific subdirectories for the sample.</span></span>  
  
2. <span data-ttu-id="3a160-111">CustomOrder.sln의 아이콘을 두 번 클릭하여 Visual Studio에서 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="3a160-111">Double-click the icon for the CustomOrder.sln to open the file in Visual Studio.</span></span>  
  
3. <span data-ttu-id="3a160-112">**빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3a160-112">In the **Build** menu, select **Build Solution**.</span></span>  
  
4. <span data-ttu-id="3a160-113">샘플 애플리케이션이 기본 \bin 또는 \bin\Debug 하위 디렉터리에 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="3a160-113">The sample application is built in the default \bin or \bin\Debug subdirectory.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a160-114">참조</span><span class="sxs-lookup"><span data-stu-id="3a160-114">See also</span></span>

- [<span data-ttu-id="3a160-115">기본 serialization</span><span class="sxs-lookup"><span data-stu-id="3a160-115">Basic Serialization</span></span>](../../../docs/standard/serialization/basic-serialization.md)
- [<span data-ttu-id="3a160-116">이진 serialization</span><span class="sxs-lookup"><span data-stu-id="3a160-116">Binary Serialization</span></span>](../../../docs/standard/serialization/binary-serialization.md)
- [<span data-ttu-id="3a160-117">특성을 사용하여 XML serialization 제어</span><span class="sxs-lookup"><span data-stu-id="3a160-117">Controlling XML Serialization Using Attributes</span></span>](../../../docs/standard/serialization/controlling-xml-serialization-using-attributes.md)
- [<span data-ttu-id="3a160-118">XML serialization 소개</span><span class="sxs-lookup"><span data-stu-id="3a160-118">Introducing XML Serialization</span></span>](../../../docs/standard/serialization/introducing-xml-serialization.md)
- [<span data-ttu-id="3a160-119">serialization</span><span class="sxs-lookup"><span data-stu-id="3a160-119">Serialization</span></span>](../../../docs/standard/serialization/index.md)
- [<span data-ttu-id="3a160-120">XML 및 SOAP serialization</span><span class="sxs-lookup"><span data-stu-id="3a160-120">XML and SOAP Serialization</span></span>](../../../docs/standard/serialization/xml-and-soap-serialization.md)
