# vlsi-half-adder
1. Half Adder using behavioral/dataflow style

library IEEE;
use IEEE.STD_LOGIC_1164.ALL;
entity half_adder is
    Port ( a : in STD_LOGIC;
           b : in STD_LOGIC;
           s : out STD_LOGIC;
           c : out STD_LOGIC);
end half_adder;

architecture Dataflow of half_adder is
begin
s<= a xor b;
c<= a and b;
end Dataflow;

Testbench for Half Adder: 
library IEEE;
use IEEE.STD_LOGIC_1164.ALL;

entity HA_tb is
--  Port ( );
end HA_tb;

architecture Behavioral of HA_tb is
component HA is
    Port ( a : in STD_LOGIC;
           b : in STD_LOGIC;
           sum : out STD_LOGIC;
           carry : out STD_LOGIC);
end component;
signal a,b,sum,carry:STD_LOGIC;

begin
U1: HA port map(a,b,sum,carry);
process
begin
a<='0';
b<='0';
wait for 100ns;
a<='0';
b<='1';
wait for 100ns;
a<='1';
b<='0';
wait for 100ns;
a<='1';
b<='1';
wait for 100ns;
end process;

end Behavioral;











