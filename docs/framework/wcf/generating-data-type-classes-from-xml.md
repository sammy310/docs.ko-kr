---
title: XML에서 데이터 형식 클래스 생성
ms.date: 03/30/2017
ms.assetid: e4e5e4e8-527f-44d1-92fa-8904a08784ea
ms.openlocfilehash: d66cbd1806b90d21a483d0c470f953ddfb9c4fca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79184129"
---
# <a name="generating-data-type-classes-from-xml"></a><span data-ttu-id="65524-102">XML에서 데이터 형식 클래스 생성</span><span class="sxs-lookup"><span data-stu-id="65524-102">Generating Data Type Classes from XML</span></span>
<span data-ttu-id="65524-103">.NET Framework 4.5에는 XML에서 데이터 형식 클래스를 생성하는 새로운 기능이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65524-103">.NET Framework 4.5 includes a new feature to generate data type classes from XML.</span></span> <span data-ttu-id="65524-104">이 항목에서는 .NET 블로그 RSS 피드에 대한 데이터 형식을 자동으로 생성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="65524-104">This topic describes how to automatically generate data types for the .NET Blog RSS feed.</span></span>  
  
### <a name="obtaining-the-xml-from-the-net-blog-rss-feed"></a><span data-ttu-id="65524-105">.NET 블로그 RSS 피드에서 XML 획득</span><span class="sxs-lookup"><span data-stu-id="65524-105">Obtaining the XML from the .NET Blog RSS feed</span></span>  
  
1. <span data-ttu-id="65524-106">인터넷 익스플로러에서 [.NET 블로그 RSS 피드로 이동합니다.](https://devblogs.microsoft.com/dotnet/feed/)</span><span class="sxs-lookup"><span data-stu-id="65524-106">In Internet Explorer, navigate to the [.NET Blog RSS feed](https://devblogs.microsoft.com/dotnet/feed/).</span></span>  
  
2. <span data-ttu-id="65524-107">페이지를 마우스 오른쪽 단추로 클릭하고 **소스 보기를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="65524-107">Right-click the page and select **View Source**.</span></span>  
  
3. <span data-ttu-id="65524-108">모든 텍스트를 선택하려면 **Ctrl+A를** 눌러 피드의 텍스트를 복사하고 **Ctrl+C를** 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="65524-108">Copy the text of the feed by pressing **Ctrl+A** to select all text, and **Ctrl+C** to copy.</span></span>  
  
### <a name="creating-the-data-types"></a><span data-ttu-id="65524-109">데이터 형식 만들기</span><span class="sxs-lookup"><span data-stu-id="65524-109">Creating the data types</span></span>  
  
1. <span data-ttu-id="65524-110">프록시를 사용할 코드 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="65524-110">Open a code file where the proxy is to be used.</span></span> <span data-ttu-id="65524-111">이 파일은 .NET Framework 4.5 프로젝트의 일부여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="65524-111">This file should be part of a .NET Framework 4.5 project.</span></span>  
  
2. <span data-ttu-id="65524-112">커서를 기존 클래스 외부에 있는 파일의 한 위치에 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="65524-112">Place the cursor in a location in the file outside any existing classes.</span></span>  
  
3. <span data-ttu-id="65524-113">**편집,** **붙여넣기 스페셜,** **클래스로 XML 붙여넣기를**선택합니다.</span><span class="sxs-lookup"><span data-stu-id="65524-113">Select **Edit**, **Paste Special**, **Paste XML as Classes**.</span></span>  
  
4. <span data-ttu-id="65524-114">클래스는 `link` `rss`" `rssChannel` `rssChannelImage` `rssChannelItem` 에서, `rssChannelItemGuid` 그리고 RSS 피드의 요소에 액세스하는 데 필요한 멤버로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="65524-114">Classes called `link`, `rss`, `rssChannel`, `rssChannelImage`, `rssChannelItem` and `rssChannelItemGuid` are created with the necessary members for accessing the elements in the RSS feed.</span></span>  
  
### <a name="using-the-generated-classes"></a><span data-ttu-id="65524-115">생성된 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="65524-115">Using the generated classes</span></span>  
  
1. <span data-ttu-id="65524-116">생성된 클래스는 다른 클래스와 마찬가지로 코드에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="65524-116">Once the classes are generated, they can be used in code like any other classes.</span></span> <span data-ttu-id="65524-117">다음 코드 예제에서는 `rssChannelImage` 클래스의 새 인스턴스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="65524-117">The following code example returns a new instance of the `rssChannelImage` class.</span></span>  
  
    ```csharp
    var channelImage = new rssChannelImage()
    {
        title = "MyImage",
        link = "http://www.contoso.com/images/channelImage.jpg",
        url = "http://www.contoso.com/entries/myEntry.html"
    };  
    ```
