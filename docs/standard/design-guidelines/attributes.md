---
title: Attributes1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- attributes [.NET Framework], about
- class library design guidelines [.NET Framework], attributes
ms.assetid: ee0038ef-b247-4747-a650-3c5c5cd58d8b
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 86fa2556e6b8fb82e31a7d4753354aa2dff627ff
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/21/2017
---
# <a name="attributes"></a><span data-ttu-id="3ff96-102">特性</span><span class="sxs-lookup"><span data-stu-id="3ff96-102">Attributes</span></span>
<span data-ttu-id="3ff96-103"><xref:System.Attribute?displayProperty=nameWithType>用于定义自定义特性的基类。</span><span class="sxs-lookup"><span data-stu-id="3ff96-103"><xref:System.Attribute?displayProperty=nameWithType> is a base class used to define custom attributes.</span></span>  
  
 <span data-ttu-id="3ff96-104">属性是可以添加到编程元素，如程序集、 类型、 成员和参数的批注。</span><span class="sxs-lookup"><span data-stu-id="3ff96-104">Attributes are annotations that can be added to programming elements such as assemblies, types, members, and parameters.</span></span> <span data-ttu-id="3ff96-105">它们存储在程序集的元数据，并可以在运行时使用反射 Api 访问。</span><span class="sxs-lookup"><span data-stu-id="3ff96-105">They are stored in the metadata of the assembly and can be accessed at runtime using the reflection APIs.</span></span> <span data-ttu-id="3ff96-106">例如，框架定义<xref:System.ObsoleteAttribute>，此方法可用于为类型或成员，以指示类型或成员已被否决。</span><span class="sxs-lookup"><span data-stu-id="3ff96-106">For example, the Framework defines the <xref:System.ObsoleteAttribute>, which can be applied to a type or a member to indicate that the type or member has been deprecated.</span></span>  
  
 <span data-ttu-id="3ff96-107">属性可以携带与属性相关的其他数据的一个或多个属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-107">Attributes can have one or more properties that carry additional data related to the attribute.</span></span> <span data-ttu-id="3ff96-108">例如，`ObsoleteAttribute`无法携带有关中的发布版本的其他信息的类型或成员已弃用并替换已过时 API 的新 Api 的说明。</span><span class="sxs-lookup"><span data-stu-id="3ff96-108">For example, `ObsoleteAttribute` could carry additional information about the release in which a type or a member got deprecated and the description of the new APIs replacing the obsolete API.</span></span>  
  
 <span data-ttu-id="3ff96-109">应用该特性，则必须指定属性的某些属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-109">Some properties of an attribute must be specified when the attribute is applied.</span></span> <span data-ttu-id="3ff96-110">这些被称为所需的属性或必需的参数，因为它们表示为从位置构造函数参数。</span><span class="sxs-lookup"><span data-stu-id="3ff96-110">These are referred to as the required properties or required arguments, because they are represented as positional constructor parameters.</span></span> <span data-ttu-id="3ff96-111">例如，<xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A>属性<xref:System.Diagnostics.ConditionalAttribute>是必需的属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-111">For example, the <xref:System.Diagnostics.ConditionalAttribute.ConditionString%2A> property of the <xref:System.Diagnostics.ConditionalAttribute> is a required property.</span></span>  
  
 <span data-ttu-id="3ff96-112">不一定需要应用了该属性指定的属性被称为可选属性 （或可选自变量）。</span><span class="sxs-lookup"><span data-stu-id="3ff96-112">Properties that do not necessarily have to be specified when the attribute is applied are called optional properties (or optional arguments).</span></span> <span data-ttu-id="3ff96-113">它们由可设置属性表示。</span><span class="sxs-lookup"><span data-stu-id="3ff96-113">They are represented by settable properties.</span></span> <span data-ttu-id="3ff96-114">编译器提供用于设置这些属性时应用的特性的特殊语法。</span><span class="sxs-lookup"><span data-stu-id="3ff96-114">Compilers provide special syntax to set these properties when an attribute is applied.</span></span> <span data-ttu-id="3ff96-115">例如，<xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType>属性表示的可选自变量。</span><span class="sxs-lookup"><span data-stu-id="3ff96-115">For example, the <xref:System.AttributeUsageAttribute.Inherited%2A?displayProperty=nameWithType> property represents an optional argument.</span></span>  
  
 <span data-ttu-id="3ff96-116">**✓ 执行**命名自定义特性类带有后缀"属性"。</span><span class="sxs-lookup"><span data-stu-id="3ff96-116">**✓ DO** name custom attribute classes with the suffix "Attribute."</span></span>  
  
 <span data-ttu-id="3ff96-117">**✓ 执行**应用<xref:System.AttributeUsageAttribute>到自定义属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-117">**✓ DO** apply the <xref:System.AttributeUsageAttribute> to custom attributes.</span></span>  
  
 <span data-ttu-id="3ff96-118">**✓ 执行**为可选自变量提供可设置属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-118">**✓ DO** provide settable properties for optional arguments.</span></span>  
  
 <span data-ttu-id="3ff96-119">**✓ 执行**提供所需的参数只获取属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-119">**✓ DO** provide get-only properties for required arguments.</span></span>  
  
 <span data-ttu-id="3ff96-120">**✓ 执行**提供构造函数参数初始化对应于所需的参数的属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-120">**✓ DO** provide constructor parameters to initialize properties corresponding to required arguments.</span></span> <span data-ttu-id="3ff96-121">每个参数应为对应的属性 （尽管具有不同大小写） 具有相同的名称。</span><span class="sxs-lookup"><span data-stu-id="3ff96-121">Each parameter should have the same name (although with different casing) as the corresponding property.</span></span>  
  
 <span data-ttu-id="3ff96-122">**请避免 x**提供构造函数参数初始化对应于可选参数的属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-122">**X AVOID** providing constructor parameters to initialize properties corresponding to the optional arguments.</span></span>  
  
 <span data-ttu-id="3ff96-123">没有换而言之，可用设置的一个构造函数和 setter 的属性。</span><span class="sxs-lookup"><span data-stu-id="3ff96-123">In other words, do not have properties that can be set with both a constructor and a setter.</span></span> <span data-ttu-id="3ff96-124">此原则使很明确的哪些参数是可选的它是必需的并可避免让两种做同样的事情。</span><span class="sxs-lookup"><span data-stu-id="3ff96-124">This guideline makes very explicit which arguments are optional and which are required, and avoids having two ways of doing the same thing.</span></span>  
  
 <span data-ttu-id="3ff96-125">**请避免 x**重载自定义特性构造函数。</span><span class="sxs-lookup"><span data-stu-id="3ff96-125">**X AVOID** overloading custom attribute constructors.</span></span>  
  
 <span data-ttu-id="3ff96-126">具有只有一个构造函数清楚地向用户的参数是必需的哪些对象是可选。</span><span class="sxs-lookup"><span data-stu-id="3ff96-126">Having only one constructor clearly communicates to the user which arguments are required and which are optional.</span></span>  
  
 <span data-ttu-id="3ff96-127">**✓ 执行**尽可能密封自定义特性类。</span><span class="sxs-lookup"><span data-stu-id="3ff96-127">**✓ DO** seal custom attribute classes, if possible.</span></span> <span data-ttu-id="3ff96-128">这使属性查找的速度更快。</span><span class="sxs-lookup"><span data-stu-id="3ff96-128">This makes the look-up for the attribute faster.</span></span>  
  
 <span data-ttu-id="3ff96-129">*部分 © 2005年，2009 Microsoft Corporation。保留所有权利。*</span><span class="sxs-lookup"><span data-stu-id="3ff96-129">*Portions © 2005, 2009 Microsoft Corporation. All rights reserved.*</span></span>  
  
 <span data-ttu-id="3ff96-130">*通过从皮尔逊教育版，Inc.的权限重新打印[Framework 设计准则： 约定、 语法和可重用.NET 库，版本 2 的模式](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619)通过 Krzysztof Cwalina 和 Brad Abrams，发布 2008 年 10 月 22，通过Microsoft Windows 开发系列的一部分的 Addison Wesley Professional。*</span><span class="sxs-lookup"><span data-stu-id="3ff96-130">*Reprinted by permission of Pearson Education, Inc. from [Framework Design Guidelines: Conventions, Idioms, and Patterns for Reusable .NET Libraries, 2nd Edition](http://www.informit.com/store/framework-design-guidelines-conventions-idioms-and-9780321545619) by Krzysztof Cwalina and Brad Abrams, published Oct 22, 2008 by Addison-Wesley Professional as part of the Microsoft Windows Development Series.*</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ff96-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3ff96-131">See Also</span></span>  
 [<span data-ttu-id="3ff96-132">框架设计指南</span><span class="sxs-lookup"><span data-stu-id="3ff96-132">Framework Design Guidelines</span></span>](../../../docs/standard/design-guidelines/index.md)  
 [<span data-ttu-id="3ff96-133">使用准则</span><span class="sxs-lookup"><span data-stu-id="3ff96-133">Usage Guidelines</span></span>](../../../docs/standard/design-guidelines/usage-guidelines.md)