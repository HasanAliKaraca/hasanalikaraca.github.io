---
id: 29
title: Dependency Inversion Principle
date: 2013-05-20T13:13:02+00:00
author: Hasan Ali Karaca
layout: post
guid: http://hasanalikaraca.com/?p=29
permalink: /2013/05/dependency-inversion-principle/
sfw_pwd:
  - G7SC1mSa06Rh
categories:
  - Design Patterns
tags:
  - dependency inversion principle
  - design patterns
---
<img style="height:300px;width:500px" src="http://ircmaxell.github.io/DontBeStupid-Presentation/assets/images/dependency_inversion_principle.jpg" alt="" />

1. ProductServiceBeforeDIP

<pre class="brush: csharp; title: ; notranslate" title="">namespace ConsoleApplication1
{
    public class ProductServiceBeforeDIP
    {
        LinqToSqlProductRepository _productRepository;

        public ProductServiceBeforeDIP()
        {
            _productRepository = new LinqToSqlProductRepository();
        }
    }
}

</pre>

2. ProductServiceAfterDIP

<pre class="brush: csharp; title: ; notranslate" title="">namespace ConsoleApplication1
{
    class ProductServiceAfterDIP
    {
        IProductRepository _productRepository;

        // using constructor to passing dependecy
        public ProductServiceAfterDIP(IProductRepository productRepository)
        {
            _productRepository = productRepository;
        }

        public void GetAll()
        {
            // getting data
        }
    }

    public interface IProductRepository
    {
        void GetAll();
    }
}
</pre>

3. Demo

<pre class="brush: csharp; title: ; notranslate" title="">namespace ConsoleApplication1
{
    class Program
    {
        static void Main(string[] args)
        {
            //1. using LinqToSql as data provider
            ProductServiceAfterDIP productService = new ProductServiceAfterDIP(new LinqToSqlProductRepository());

            productService.GetAll();

            //2. using EF as data provider
            productService = new ProductServiceAfterDIP(new EntityFrameWorkProductRepository());

            productService.GetAll();
        }
    }

    public class EntityFrameWorkProductRepository : IProductRepository
    {
        #region IProductRepository Members

        public void GetAll()
        {
            // getting data with ef
        }

        #endregion
    }

    public class LinqToSqlProductRepository : IProductRepository
    {
        #region IProductRepository Members

        public void GetAll()
        {
            // getting data with LinQtoSql
        }

        #endregion
    }
}
</pre>
 