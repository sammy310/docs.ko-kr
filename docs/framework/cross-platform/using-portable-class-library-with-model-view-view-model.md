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
# <a name="using-portable-class-library-with-model-view-view-model"></a>Model-View-View Model과 함께 이식 가능한 클래스 라이브러리 사용

.NET Framework [이식 가능한 클래스 라이브러리](portable-class-library.md)를 사용하여 MVVM(Model-View-View Model) 패턴을 구현하고 여러 플랫폼 간에 어셈블리를 공유할 수 있습니다.

[!INCLUDE[standard](../../../includes/pcl-to-standard.md)]

 MVVM은 내부 비즈니스 논리에서 사용자 인터페이스를 분리하는 애플리케이션 패턴입니다. Visual Studio 2012의 이식 가능한 클래스 라이브러리 프로젝트에서 모델을 구현하고 모델 클래스를 본 다음, 여러 플랫폼을 위해 사용자 지정된 뷰를 만들 수 있습니다. 이 접근 방식을 사용하면 한 번만 데이터 모델과 비즈니스 논리를 작성하고, 다음 설명에서와 같이 .NET Framework, Silverlight, Windows Phone 및 Windows 8.x 스토어 앱의 해당 코드를 사용할 수 있습니다.

 ![MVVM을 통해 플랫폼 간에 어셈블리를 공유하는 이식 가능한 클래스 라이브러리를 보여 줍니다.](./media/using-portable-class-library-with-model-view-view-model/mvvm-share-assemblies-across-platforms.png)

 이 항목에서는 MVVM 패턴에 대한 일반 정보를 제공하지 않습니다. 이식 가능한 클래스 라이브러리를 사용하여 MVVM를 구현하는 방법에 대한 정보만 제공합니다. MVVM에 대한 자세한 내용은 [WPF용 프리즘 라이브러리 5.0을 사용한 MVVM 빠른 시작](/previous-versions/msp-n-p/gg430857(v=pandp.40))을 참조하세요.

## <a name="classes-that-support-mvvm"></a>MVVM을 지원하는 클래스

 이식 가능한 클래스 라이브러리 프로젝트에서 .NET Framework 4.5, Windows 8.x 스토어 앱용 .NET, Silverlight 또는 Windows Phone 7.5를 대상으로 하는 경우 MVVM 패턴을 구현하는 데 다음 클래스를 사용할 수 있습니다.

- <xref:System.Collections.ObjectModel.ObservableCollection%601?displayProperty=nameWithType> 클래스

- <xref:System.Collections.ObjectModel.ReadOnlyObservableCollection%601?displayProperty=nameWithType> 클래스

- <xref:System.Collections.Specialized.INotifyCollectionChanged?displayProperty=nameWithType> 클래스

- <xref:System.Collections.Specialized.NotifyCollectionChangedAction?displayProperty=nameWithType> 클래스

- <xref:System.Collections.Specialized.NotifyCollectionChangedEventArgs?displayProperty=nameWithType> 클래스

- <xref:System.Collections.Specialized.NotifyCollectionChangedEventHandler?displayProperty=nameWithType> 클래스

- <xref:System.ComponentModel.DataErrorsChangedEventArgs?displayProperty=nameWithType> 클래스

- <xref:System.ComponentModel.INotifyDataErrorInfo?displayProperty=nameWithType> 클래스

- <xref:System.ComponentModel.INotifyPropertyChanged?displayProperty=nameWithType> 클래스

- <xref:System.Windows.Input.ICommand?displayProperty=nameWithType> 클래스

- <xref:System.ComponentModel.DataAnnotations?displayProperty=nameWithType> 네임스페이스의 모든 클래스

## <a name="implementing-mvvm"></a>MVVM 구현

 MVVM을 구현하려면 일반적으로 이식 가능한 클래스 라이브러리 프로젝트에서 모델 및 뷰 모델을 만듭니다. 이식 가능한 클래스 라이브러리 프로젝트에서 이식 불가능한 프로젝트를 참조할 수 없기 때문입니다. 모델 및 뷰 모델은 동일한 프로젝트에 있거나 별도의 프로젝트에 있을 수 있습니다. 별도의 프로젝트를 사용하는 경우 뷰 모델 프로젝트의 참조를 모델 프로젝트에 추가합니다.

 모델 및 뷰 모델 프로젝트를 컴파일한 후에 뷰를 포함하는 앱에서 해당 어셈블리를 참조합니다. 뷰가 뷰 모델과만 상호 작용하는 경우 뷰 모델을 포함하는 어셈블리만 참조하면 됩니다.

### <a name="model"></a>모델

 다음 예제에서는 이식 가능한 클래스 라이브러리 프로젝트에 있을 수 있는 간단한 모델 클래스를 보여 줍니다.

 [!code-csharp[PortableClassLibraryMVVM#1](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customer.cs#1)]
 [!code-vb[PortableClassLibraryMVVM#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customer.vb#1)]

 다음 예제에서는 이식 가능한 클래스 라이브러리 프로젝트에서 데이터를 채우고, 검색하고, 업데이트하는 간단한 방법을 보여 줍니다. 실제 앱에서는 WCF(Windows Communication Foundation) 서비스와 같은 소스에서 데이터를 검색합니다.

 [!code-csharp[PortableClassLibraryMVVM#2](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/customerrepository.cs#2)]
 [!code-vb[PortableClassLibraryMVVM#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerrepository.vb#2)]

### <a name="view-model"></a>뷰 모델

 MVVM 패턴을 구현할 때 뷰 모델에 대한 기본 클래스가 자주 추가됩니다. 다음 예제에서는 기본 클래스를 보여 줍니다.

 [!code-csharp[PortableClassLibraryMVVM#3](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/viewmodelbase.cs#3)]
 [!code-vb[PortableClassLibraryMVVM#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/viewmodelbase.vb#3)]

 <xref:System.Windows.Input.ICommand> 인터페이스의 구현은 MVVM 패턴에 자주 사용됩니다. 다음 예제에서는 <xref:System.Windows.Input.ICommand> 인터페이스의 구현을 보여 줍니다.

 [!code-csharp[PortableClassLibraryMVVM#4](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/relaycommand.cs#4)]
 [!code-vb[PortableClassLibraryMVVM#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/relaycommand.vb#4)]

 다음 예제에서는 간단한 뷰 모델을 보여줍니다.

 [!code-csharp[PortableClassLibraryMVVM#5](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainpageviewmodel.cs#5)]
 [!code-vb[PortableClassLibraryMVVM#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR/portableclasslibrarymvvm/vb/customerviewmodel.vb#5)]  
  
### <a name="view"></a>보기  

 .NET Framework 4.5 앱, Windows 8.x 스토어 앱, Silverlight 기반 앱 또는 Windows Phone 7.5 앱에서 모델 및 뷰 모델 프로젝트를 포함하는 어셈블리를 참조할 수 있습니다.  그런 다음 뷰 모델과 상호 작용하는 뷰를 만듭니다. 다음 예제에서는 뷰 모델에서 데이터를 검색하고 업데이트하는 간단한 WPF(Windows Presentation Foundation) 앱을 보여 줍니다. Silverlight, Windows Phone 또는 Windows 8.x 스토어 앱에서 비슷한 뷰를 만들 수 있습니다.  
  
 [!code-xaml[PortableClassLibraryMVVM#6](../../../samples/snippets/csharp/VS_Snippets_CLR/portableclasslibrarymvvm/cs/mainwindow.xaml#6)]  
  
## <a name="see-also"></a>참고 항목

- [이식 가능한 클래스 라이브러리](portable-class-library.md)
