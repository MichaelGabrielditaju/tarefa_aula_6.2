# Projeto de Controle de Servomotor e LED RGB

## Descrição

Este projeto implementa o controle de um servomotor utilizando PWM (Modulação por Largura de Pulso) na GPIO 22 e manipulação de um LED RGB na GPIO 12. O código foi desenvolvido para atender a requisitos específicos de movimentação do servomotor e controle da intensidade luminosa do LED RGB.

## Funcionamento do Código

### Controle do Servomotor

O código utiliza a biblioteca `hardware/pwm` para configurar a GPIO 22 como saída PWM. A frequência do PWM é definida para aproximadamente 50 Hz (período de 20 ms) com o uso da função `pwm_set_clkdiv`. O ciclo ativo do PWM é ajustado para posicionar o servomotor em três ângulos diferentes:

1. **180 graus**: O ciclo ativo é definido para 2400 µs, mantendo a posição por 5 segundos.
2. **90 graus**: O ciclo ativo é reduzido para 1470 µs, com nova espera de 5 segundos.
3. **0 graus**: O ciclo ativo é ajustado para 500 µs, seguido de mais 5 segundos de espera.

Após essas movimentações, o código inicia um ciclo de movimentação suave, variando o ângulo entre 0 e 180 graus. A suavidade da movimentação é garantida por incrementos de ±5 µs no ciclo ativo, com um atraso de 10 ms entre cada ajuste.

### Controle do LED RGB

A manipulação do LED RGB é realizada na GPIO 12. O comportamento observado ao controlar a intensidade luminosa do LED é o seguinte:

- **Potência Máxima**: O LED é ligado na sua potência máxima inicialmente.
- **Potência Média**: Após 5 segundos, a intensidade do LED é reduzida para a potência média.
- **Potência Mínima**: Após mais 5 segundos, o LED atinge sua potência mínima.

Após estas alterações, a luz do LED começa a variar sua intensidade entre o máximo e o mínimo, proporcionando um efeito visual dinâmico.

## Análise das Soluções Criadas

O código atende de forma eficiente aos requisitos estabelecidos. A configuração do PWM é adequada para o controle preciso do servomotor, permitindo ajustes finos na posição. A lógica implementada para o controle do LED RGB oferece um bom exemplo de como combinar diferentes componentes em um sistema embarcado.

### Observações

As variações de intensidade do LED RGB, além de serem visualmente interessantes, podem ser utilizadas para indicar estados diferentes do sistema ou para dar feedback ao usuário.

## Link Para o Vídeo no YouTube:
Link: https://youtu.be/koPOoyI0szo?si=xewYS8u4OIIxQxZ8