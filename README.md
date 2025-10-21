# Nachapa[Index.tsx](https://github.com/user-attachments/files/23012416/Index.tsx)
import { Link } from "react-router-dom";
import { Button } from "@/components/ui/button";
import { ArrowRight, Clock, Star, Truck } from "lucide-react";
import Navbar from "@/components/Navbar";
import heroBurger from "@/assets/hero-burger.jpg";

const Index = () => {
  const features = [
    {
      icon: Clock,
      title: "Entrega Rápida",
      description: "Seu pedido em até 40 minutos",
    },
    {
      icon: Star,
      title: "Qualidade Premium",
      description: "Ingredientes selecionados",
    },
    {
      icon: Truck,
      title: "Acompanhe seu Pedido",
      description: "Rastreamento em tempo real",
    },
  ];

  return (
    <div className="min-h-screen">
      <Navbar />
      
      {/* Hero Section */}
      <section className="relative min-h-[90vh] flex items-center overflow-hidden">
        <div className="absolute inset-0 gradient-hero opacity-95" />
        <div className="absolute inset-0">
          <img
            src={heroBurger}
            alt="Delicious burger"
            className="h-full w-full object-cover opacity-20"
          />
        </div>
        
        <div className="container relative z-10 mx-auto px-4">
          <div className="max-w-2xl">
            <h1 className="mb-6 text-5xl font-bold text-primary-foreground md:text-7xl">
              Os Melhores Hambúrgueres da Cidade
            </h1>
            <p className="mb-8 text-xl text-primary-foreground/90 md:text-2xl">
              Sabor incomparável, ingredientes frescos e entrega rápida. Peça agora e descubra!
            </p>
            <div className="flex flex-col gap-4 sm:flex-row">
              <Link to="/cardapio">
                <Button variant="hero" size="lg" className="w-full sm:w-auto gap-2">
                  Ver Cardápio
                  <ArrowRight className="h-5 w-5" />
                </Button>
              </Link>
              <Link to="/auth">
                <Button variant="outline" size="lg" className="w-full sm:w-auto bg-background/10 backdrop-blur border-primary-foreground/20 text-primary-foreground hover:bg-background/20">
                  Criar Conta
                </Button>
              </Link>
            </div>
          </div>
        </div>
      </section>

      {/* Features Section */}
      <section className="py-20 bg-muted/30">
        <div className="container mx-auto px-4">
          <h2 className="mb-12 text-center text-3xl font-bold md:text-4xl">
            Por que escolher a BurgerHub?
          </h2>
          <div className="grid gap-8 md:grid-cols-3">
            {features.map((feature, index) => {
              const Icon = feature.icon;
              return (
                <div
                  key={index}
                  className="flex flex-col items-center text-center p-6 rounded-lg bg-card shadow-card hover:shadow-glow transition-all duration-300 hover:scale-105"
                >
                  <div className="mb-4 flex h-16 w-16 items-center justify-center rounded-full bg-primary/10">
                    <Icon className="h-8 w-8 text-primary" />
                  </div>
                  <h3 className="mb-2 text-xl font-bold">{feature.title}</h3>
                  <p className="text-muted-foreground">{feature.description}</p>
                </div>
              );
            })}
          </div>
        </div>
      </section>

      {/* CTA Section */}
      <section className="py-20 gradient-primary">
        <div className="container mx-auto px-4 text-center">
          <h2 className="mb-4 text-3xl font-bold text-primary-foreground md:text-4xl">
            Pronto para experimentar?
          </h2>
          <p className="mb-8 text-xl text-primary-foreground/90">
            Faça seu pedido agora e receba em minutos!
          </p>
          <Link to="/cardapio">
            <Button variant="outline" size="lg" className="bg-background text-primary hover:bg-background/90">
              Pedir Agora
            </Button>
          </Link>
        </div>
      </section>

      {/* Footer */}
      <footer className="border-t border-border py-8 bg-card">
        <div className="container mx-auto px-4 text-center text-muted-foreground">
          <p>© 2025 BurgerHub. Todos os direitos reservados.</p>
        </div>
      </footer>
    </div>
  );
};

export default Index;
