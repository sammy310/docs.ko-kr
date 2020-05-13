---
title: '방법: 지역화할 수 있는 애플리케이션에서 리소스 사용'
ms.date: 03/30/2017
helpviewer_keywords:
- applications [WPF], localizable
- localizable applications [WPF]
ms.assetid: 08539ad6-7fca-4f34-b82b-ff439e11dfa7
ms.openlocfilehash: 8f516a86036656b98add23d38c588b5c19be4d7a
ms.sourcegitcommit: 488aced39b5f374bc0a139a4993616a54d15baf0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/12/2020
ms.locfileid: "83212477"
---
# <a name="how-to-use-resources-in-localizable-apps"></a><span data-ttu-id="bda2c-102">방법: 지역화할 수 있는 응용 프로그램에서 리소스 사용</span><span class="sxs-lookup"><span data-stu-id="bda2c-102">How to: Use resources in localizable apps</span></span>

<span data-ttu-id="bda2c-103">지역화는 사용자 인터페이스를 다양 한 문화권에 맞게 조정 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-103">Localization means to adapt a user interface to different cultures.</span></span> <span data-ttu-id="bda2c-104">이렇게 하려면 제목, 캡션 및 목록 상자 항목과 같은 텍스트를 번역 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-104">To do this, text such as titles, captions, and list box items must be translated.</span></span> <span data-ttu-id="bda2c-105">번역을 더 쉽게 수행 하기 위해 번역할 항목이 리소스 파일로 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-105">To make translation easier, the items to be translated are collected into resource files.</span></span> <span data-ttu-id="bda2c-106">지역화를 위한 리소스 파일을 만드는 방법에 대 한 자세한 내용은 [응용 프로그램 지역화](how-to-localize-an-application.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bda2c-106">See [Localize an app](how-to-localize-an-application.md) for information on how to create a resource file for localization.</span></span> <span data-ttu-id="bda2c-107">WPF 응용 프로그램을 지역화 가능 하 게 만들려면 개발자가 지역화 가능한 리소스를 모두 리소스 어셈블리에 빌드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-107">To make a WPF application localizable, developers need to build all the localizable resources into a resource assembly.</span></span> <span data-ttu-id="bda2c-108">리소스 어셈블리는 다른 언어로 지역화 되며 코드 숨김이 리소스 관리 API를 사용 하 여 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-108">The resource assembly is localized into different languages, and the code-behind uses resource management API to load.</span></span>

## <a name="example"></a><span data-ttu-id="bda2c-109">예제</span><span class="sxs-lookup"><span data-stu-id="bda2c-109">Example</span></span>

<span data-ttu-id="bda2c-110">WPF 응용 프로그램에 필요한 파일 중 하나는 프로젝트 파일 (proj)입니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-110">One of the files required for a WPF application is a project file (.proj).</span></span> <span data-ttu-id="bda2c-111">애플리케이션에서 사용하는 모든 리소스는 프로젝트 파일에 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-111">All resources that you use in your application should be included in the project file.</span></span> <span data-ttu-id="bda2c-112">다음 XAML 예제에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-112">The following XAML example shows this.</span></span>

```xaml
<Resource Include="data\picture1.jpg"/>  
<EmbeddedResource Include="data\stringtable.en-US.restext"/>
```

<span data-ttu-id="bda2c-113">응용 프로그램에서 리소스를 사용 하려면 사용 하려는 <xref:System.Resources.ResourceManager> 리소스를 인스턴스화하고 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-113">To use a resource in your application, instantiate <xref:System.Resources.ResourceManager> and load the resource you want to use.</span></span> <span data-ttu-id="bda2c-114">다음 c # 코드에서는이 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bda2c-114">The following C# code demonstrates how to do this.</span></span>

[!code-csharp[LocalizationResources#2](~/samples/snippets/csharp/VS_Snippets_Wpf/LocalizationResources/CSharp/page1.xaml.cs#2)]

## <a name="see-also"></a><span data-ttu-id="bda2c-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bda2c-115">See also</span></span>

- [<span data-ttu-id="bda2c-116">앱 지역화</span><span class="sxs-lookup"><span data-stu-id="bda2c-116">Localize an app</span></span>](how-to-localize-an-application.md)
