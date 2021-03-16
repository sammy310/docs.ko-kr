---
description: '자세한 정보: Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용'
title: Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용
ms.date: 07/18/2018
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Portable Class Library [.NET Framework], and MVVM
- MVVM, and Portable Class Library
ms.assetid: 41a0b9f8-15a2-431a-bc35-e310b2953b03
ms.openlocfilehash: 4eea099aaa515c2b7d9874fd6c6d5c4132c5e7a2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "102402261"
---
# <a name="using-portable-class-library-with-model-view-view-model"></a><span data-ttu-id="f841a-103">Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="f841a-103">Using Portable Class Library with Model-View-View Model</span></span>

<span data-ttu-id="f841a-104">.NET Framework [이식 가능한 클래스 라이브러리](portable-class-library.md)를 사용하여 MVVM(Model-View-View Model) 패턴을 구현하고 여러 플랫폼 간에 어셈블리를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-104">You can use the .NET Framework [Portable Class Library](portable-class-library.md) to implement the Model-View-View Model (MVVM) pattern and share assemblies across multiple platforms.</span></span>

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 <span data-ttu-id="f841a-105">MVVM은 내부 비즈니스 논리에서 사용자 인터페이스를 분리하는 애플리케이션 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-105">MVVM is an application pattern that isolates the user interface from the underlying business logic.</span></span> <span data-ttu-id="f841a-106">Visual Studio 2012의 이식 가능한 클래스 라이브러리 프로젝트에서 모델을 구현하고 모델 클래스를 본 다음, 여러 플랫폼을 위해 사용자 지정된 뷰를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-106">You can implement the model and view model classes in a Portable Class Library project in Visual Studio 2012, and then create views that are customized for different platforms.</span></span> <span data-ttu-id="f841a-107">이 접근 방식을 사용하면 한 번만 데이터 모델과 비즈니스 논리를 작성하고, 다음 설명에서와 같이 .NET Framework, Silverlight, Windows Phone 및 Windows 8.x 스토어 앱의 해당 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-107">This approach enables you to write the data model and business logic only once, and use that code from .NET Framework, Silverlight, Windows Phone, and Windows 8.x Store apps, as shown in the following illustration.</span></span>

 ![MVVM을 통해 플랫폼 간에 어셈블리를 공유하는 이식 가능한 클래스 라이브러리를 보여 줍니다.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 <span data-ttu-id="f841a-109">이 항목에서는 MVVM 패턴에 대한 일반 정보를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-109">This topic does not provide general information about the MVVM pattern.</span></span> <span data-ttu-id="f841a-110">이식 가능한 클래스 라이브러리를 사용하여 MVVM를 구현하는 방법에 대한 정보만 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-110">It only provides information about how to use Portable Class Library to implement MVVM.</span></span> <span data-ttu-id="f841a-111">MVVM에 대한 자세한 내용은 [WPF용 프리즘 라이브러리 5.0을 사용한 MVVM 빠른 시작](/previous-versions/msp-n-p/gg430857(v=pandp.40))을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f841a-111">For more information about MVVM, see the [MVVM Quickstart Using the Prism Library 5.0 for WPF](/previous-versions/msp-n-p/gg430857(v=pandp.40)).</span></span>

## <a name="classes-that-support-mvvm"></a><span data-ttu-id="f841a-112">MVVM을 지원하는 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-112">Classes That Support MVVM</span></span>

 <span data-ttu-id="f841a-113">이식 가능한 클래스 라이브러리 프로젝트에서 .NET Framework 4.5, Windows 8.x 스토어 앱용 .NET, Silverlight 또는 Windows Phone 7.5를 대상으로 하는 경우 MVVM 패턴을 구현하는 데 다음 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-113">When you target the .NET Framework 4.5, .NET for Windows 8.x Store apps, Silverlight, or Windows Phone 7.5 for your Portable Class Library project, the following classes are available for implementing the MVVM pattern:</span></span>

- <span data-ttu-id="f841a-114"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-114"><xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-115"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-115"><xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-116"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-116"><xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-117"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-117"><xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-118"><xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-119"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-119"><xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-120"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-120"><xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-121"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-121"><xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-122"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-122"><xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-123"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-123"><xref:System.Windows.Input.ICommand?displayProperty=nameWithType> class</span></span>

- <span data-ttu-id="f841a-124"><xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> 네임스페이스의 모든 클래스</span><span class="sxs-lookup"><span data-stu-id="f841a-124">All classes in the <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> namespace</span></span>

## <a name="implementing-mvvm"></a><span data-ttu-id="f841a-125">MVVM 구현</span><span class="sxs-lookup"><span data-stu-id="f841a-125">Implementing MVVM</span></span>

 <span data-ttu-id="f841a-126">MVVM을 구현하려면 일반적으로 이식 가능한 클래스 라이브러리 프로젝트에서 모델 및 뷰 모델을 만듭니다. 이식 가능한 클래스 라이브러리 프로젝트에서 이식 불가능한 프로젝트를 참조할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-126">To implement MVVM, you typically create both the model and the view model in a Portable Class Library project, because a Portable Class Library project cannot reference a non-portable project.</span></span> <span data-ttu-id="f841a-127">모델 및 뷰 모델은 동일한 프로젝트에 있거나 별도의 프로젝트에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-127">The model and view model can be in the same project or in separate projects.</span></span> <span data-ttu-id="f841a-128">별도의 프로젝트를 사용하는 경우 뷰 모델 프로젝트의 참조를 모델 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-128">If you use separate projects, add a reference from the view model project to the model project.</span></span>

 <span data-ttu-id="f841a-129">모델 및 뷰 모델 프로젝트를 컴파일한 후에 뷰를 포함하는 앱에서 해당 어셈블리를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-129">After you compile the model and view model projects, you reference those assemblies in the app that contains the view.</span></span> <span data-ttu-id="f841a-130">뷰가 뷰 모델과만 상호 작용하는 경우 뷰 모델을 포함하는 어셈블리만 참조하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-130">If the view interacts only with the view model, you only have to reference the assembly that contains the view model.</span></span>

### <a name="model"></a><span data-ttu-id="f841a-131">모델</span><span class="sxs-lookup"><span data-stu-id="f841a-131">Model</span></span>

 <span data-ttu-id="f841a-132">다음 예제에서는 이식 가능한 클래스 라이브러리 프로젝트에 있을 수 있는 간단한 모델 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-132">The following example shows a simplified model class that could reside in a Portable Class Library project.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 <span data-ttu-id="f841a-133">다음 예제에서는 이식 가능한 클래스 라이브러리 프로젝트에서 데이터를 채우고, 검색하고, 업데이트하는 간단한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-133">The following example shows a simple way to populate, retrieve, and update the data in a Portable Class Library project.</span></span> <span data-ttu-id="f841a-134">실제 앱에서는 WCF(Windows Communication Foundation) 서비스와 같은 소스에서 데이터를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-134">In a real app, you would retrieve the data from a source such as a Windows Communication Foundation (WCF) service.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a><span data-ttu-id="f841a-135">뷰 모델</span><span class="sxs-lookup"><span data-stu-id="f841a-135">View Model</span></span>

 <span data-ttu-id="f841a-136">MVVM 패턴을 구현할 때 뷰 모델에 대한 기본 클래스가 자주 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-136">A base class for view models is frequently added when implementing the MVVM pattern.</span></span> <span data-ttu-id="f841a-137">다음 예제에서는 기본 클래스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-137">The following example shows a base class.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <span data-ttu-id="f841a-138"><xref:System.Windows.Input.ICommand> 인터페이스의 구현은 MVVM 패턴에 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-138">An implementation of the <xref:System.Windows.Input.ICommand> interface is frequently used with the MVVM pattern.</span></span> <span data-ttu-id="f841a-139">다음 예제에서는 <xref:System.Windows.Input.ICommand> 인터페이스의 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-139">The following example shows an implementation of the <xref:System.Windows.Input.ICommand> interface.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 <span data-ttu-id="f841a-140">다음 예제에서는 간단한 뷰 모델을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-140">The following example shows a simplified view model.</span></span>

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a><span data-ttu-id="f841a-141">보기</span><span class="sxs-lookup"><span data-stu-id="f841a-141">View</span></span>  

 <span data-ttu-id="f841a-142">.NET Framework 4.5 앱, Windows 8.x 스토어 앱, Silverlight 기반 앱 또는 Windows Phone 7.5 앱에서 모델 및 뷰 모델 프로젝트를 포함하는 어셈블리를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-142">From a .NET Framework 4.5 app, Windows 8.x Store app, Silverlight-based app, or Windows Phone 7.5 app, you can reference the assembly that contains the model and view model projects.</span></span>  <span data-ttu-id="f841a-143">그런 다음 뷰 모델과 상호 작용하는 뷰를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-143">You then create a view that interacts with the view model.</span></span> <span data-ttu-id="f841a-144">다음 예제에서는 뷰 모델에서 데이터를 검색하고 업데이트하는 간단한 WPF(Windows Presentation Foundation) 앱을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-144">The following example shows a simplified Windows Presentation Foundation (WPF) app that retrieves and updates data from the view model.</span></span> <span data-ttu-id="f841a-145">Silverlight, Windows Phone 또는 Windows 8.x 스토어 앱에서 비슷한 뷰를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f841a-145">You could create similar views in Silverlight, Windows Phone, or Windows 8.x Store apps.</span></span>  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a><span data-ttu-id="f841a-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f841a-146">See also</span></span>

- [<span data-ttu-id="f841a-147">이식 가능한 클래스 라이브러리</span><span class="sxs-lookup"><span data-stu-id="f841a-147">Portable Class Library</span></span>](portable-class-library.md)
